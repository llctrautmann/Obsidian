---
title: Pseudo Random Numbers in JAX
date:
  - 12-04-2024
time: 11:56
author: Luca Trautmann
tags:
  - "#jax"
series: JAX
chapter: 
status: Incomplete
modified: 2024-04-12
---
# Pseudo Random Numbers in JAX
Random numbers need to be generated differently as they also need to be stateless: 

The general procedure for key generation is the following: 
```python

rng = jax.random.PRNGKey(seed=451)

key1, key2, ... , key_n = jax.random.split(rng)


```