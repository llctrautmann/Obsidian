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

## Caching
`jax.jit` using caching to retain to maintain values, which can lead to strange behaviour if unaccounted for. 

Suppose I define `f = jax.jit(g)`. When I first invoke `f`, it will get compiled, and the resulting XLA code will get cached. Subsequent calls of `f` will reuse the cached code. This is how `jax.jit` makes up for the up-front cost of compilation.

If I specify `static_argnums`, then the cac
 
