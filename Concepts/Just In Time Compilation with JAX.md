---
title: Just In Time Compilation with JAX
date:
  - 10-04-2024
time: 18:46
author: Luca Trautmann
tags: 
series: 
chapter: 
status: Incomplete
modified: 2024-04-11
---
# Just In Time Compilation with JAX
In this section, I will further explore how JAX works, and how we can make it performant. I will discuss the `jax.jit()` transform, which will perform _Just In Time_ (JIT) compilation of a JAX Python function so it can be executed efficiently in XLA.

## How JAX transforms work
JAX is designed to only understand side-effect effect free code [[Jax as Accelerated Numpy]]. Of course, impure functions can still be written and even run, but JAX gives **no guarantees** about their behaviour once converted to jaxpr.

## Shapes matter, inputs corrupt
The default level that `jax.jit` uses is `ShapedArray` - the tracer will trace the shape but not the value. This means that as long as the input shape stays the same, any value can be put in the jit-compiled function.

This also means that compiling a function that is conditioned on a specific value, we will get an error. This can be mitigated with `static_argnames` but requires careful considerations, as large numbers of `static_argnames` will lead to a lot of overhead as the graph needs to be constructed for each value. 

## When to use JIT
Ideally I want to use `jit` as much as possible for the biggest performance benefits. Therefore, it usually only saves time if the compiled function is complex and you will run it numerous times. Fortunately, this is common in machine learning, where we tend to compile a large, complicated model, then run it for millions of iterations.

## Caching
`jax.jit` using caching to retain to maintain values, which can lead to strange behaviour if unaccounted for. 

Suppose I define `f = jax.jit(g)`. When I first invoke `f`, it will get compiled, and the resulting XLA code will get cached. Subsequent calls of `f` will reuse the cached code. This is how `jax.jit` makes up for the up-front cost of compilation.

If I specify `static_argnums`, then the cached code will be used only for the same value labelled as static. 
 
