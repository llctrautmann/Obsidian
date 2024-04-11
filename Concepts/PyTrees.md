---
title: PyTrees
date:
  - 10-04-2024
time: 14:07
author: Luca Trautmann
tags:
  - jax
series: JAX
chapter: 
status: Incomplete
modified: 2024-04-11
---
# PyTrees: Making Arguments Bearable

> a Pytree is a container of leaf elements and/or more Pytrees. Containers include lists, tuples, and dicts. A leaf element is anything that’s not a Pytree, e.g. an array. In other words, a Pytree is just a possibly-nested standard or user-registered Python container. If nested, note that the container types do not need to match. A single “leaf”, i.e. a non-container object, is also considered a pytree. (Docs)

By default, the PyTree registry includes the class `list`. `tuple`, and `dict`. Any other object not in the registry will be considered a leaf in the PyTree structure. Other PyTrees can be added into an existing PyTree to form a nested PyTree. 

Under the hood, a `jit`-compiled function will look for a cached PyTree structure and use it in the case where an existing cached structure exists. 

## Where do you find PyTrees in ML Dataflows
In machine learning, some places where you commonly find pytrees are:

- Model parameters
- Dataset entries
- RL agent observations 

They also often arise naturally when working in bulk with datasets (e.g., lists of lists of dicts).

```python
list_of_lists = [
    [1, 2, 3],
    {'weights': [1,2,3], 'bias': ["a", "b", "c"]},
    [3, 4]
]

jax.tree_map(lambda x: x*2, list_of_lists)

>>> [[2, 4, 6], {'bias': ['aa', 'bb', 'cc'], 'weights': [2, 4, 6]}, [6, 8]]

another_list_of_lists = list_of_lists
jax.tree_map(lambda x, y: x+y, list_of_lists, another_list_of_lists)

>>> [[2, 4, 6], [2, 4], [2, 4, 6, 8]]

# When using multiple arguments with `jax.tree_map`, the structure of the inputs must exactly match. That is, lists must have the same number of elements, dicts must have the same keys, etc.
```


## Example: ML model parameters

