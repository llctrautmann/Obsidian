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
sum_of_squares_dx = jax.grad(sum_of_squares) # returns the gradient 2x

x = jnp.asarray([1.0, 2.0, 3.0, 4.0])

print(sum_of_squares(x))
print(sum_of_squares_dx(x))

>>> 30.0
>>> [2. 4. 6. 8.]
```

The analog in [[Vector Calculus]] is the vector gradient:

$$
(\nabla f)(x)_i=\frac{\partial f}{\partial x_i}(x) .
$$

So, `jax.grad(f)` is the function that computes the gradient, so `jax.grad(f)(x)` is the gradient of `f` at `x`. The JAX API works directly with functions, staying closer to the underlying math. Once I become accustomed to this way of doing things, it `should` feel natural: my loss function in code really is a function of parameters and data, and you find its gradient just like you would in the math.

`jax.grad()` will always find the gradient wrt. to the first argument. I can mitigate this by using `argnums=(0,1,...,arg_n)` in the `grad` function wrapper. 

```python
def sum_squared_error(x, y):
  return jnp.sum((x-y)**2)

sum_squared_error_dx = jax.grad(sum_squared_error)

y = jnp.asarray([1.1, 2.1, 3.1, 4.1])

print(sum_squared_error_dx(x, y))

>>> [-0.20000005 -0.19999981 -0.19999981 -0.19999981]

jax.grad(sum_squared_error, argnums=(0, 1))(x, y) 
# Find gradient wrt both x & y

>>> (Array([-0.20000005, -0.19999981, -0.19999981, -0.19999981], dtype=float32),
... Array([0.20000005, 0.19999981, 0.19999981, 0.19999981], dtype=float32))
```

PyTrees make this easier and in general the structure I am looking for is 
```python
def loss_fn(params, data):
	...

	grads. = jax.grad(loss_fn)(params, data_batch)
	# params here will be the pytree structure
```

### Value and Grad
In the case where I need to find the value and the gradient of a function I can use `jax.value_and_grad(<func>)(*args)`.

```python
jax.value_and_grad(sum_squared_error)(x, y)

# This returns
jax.value_and_grad(f)(*xs) == (f(*xs), jax.grad(f)(*xs)) 
```

### Auxiliary Data
`grad` is not able to return multiple values but only scalar values. The argument `has_aux=True` allow to return auxiliary data. The returned data is in the form `(out, aux)`. 

## Differences from NumPy
The main difference between NumPy and JAX is the functional programming paradigm that underpins JAX. This means: 

**!!! Don't write code with side effects !!!**

A side-effect is any effect of a function that does not appear in it's output. Here are some examples: 

> [!Modifying in-place] 
> ```python
> import numpy as np 
> 
> x = np.array([1, 2, 3])
> def in_place_modify(x):
> 	x[0] = 123
> 	return None
> ```
> This works in numpy but cannot work in JAX. The solution here is to use `jnp.ndarray.at` 
> 
> ```python
> def jax_in_place_modify(x):
> 	return x.at[0].set(123)
> ```
> This will work but it creates a new array and leaves the old array untouched. 

Side-effect-free code is sometimes called _functionally pure_, or just _pure_. As a rule of thumb, any functions intended to be transformed by JAX should avoid side-effects, and the JAX primitives themselves will try to help you do that.


 


 




 


