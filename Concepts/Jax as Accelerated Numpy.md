---
title: Jax as Accelerated Numpy
date:
  - 10-04-2024
time: 13:45
author: Luca Trautmann
tags:
  - jax
series: JAX
chapter: 1
status: Incomplete
modified: 2024-04-10
---
# Jax as Accelerated Numpy
The main point behind jax is its speed, as every operation is done on the accelerator that is attached to the underlying code accelerator such as the GPU or TPU. This should in most cases make the code run a lot faster, as everything stays on the vRAM of the hardware, instead of being shifted between the accelerated devices. 

## `Grad()`: The first transformation
Fundamentally `JAX` allows me to transform functions into much faster executing code. The most commonly used transformation is `jax.grad()`.

`jax.grad()` takes a numerical function written in python and returns a new function that computes the gradients of the function. 

```python
def sum_of_squares(x):
	return jnp.sum(x**2)
```

```python
sum_of_squares_dx = jax.grad(sum_of_squares) # returns the gradient

x = jnp.asarray([1.0, 2.0, 3.0, 4.0])

print(sum_of_squares(x))
print(sum_of_squares_dx(x))

>>> 30.0
>>> [2. 4. 6. 8.]
```


