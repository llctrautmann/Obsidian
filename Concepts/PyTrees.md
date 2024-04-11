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
modified: 2024-04-10
---
# PyTrees: Making Arguments Bearable

> The formal definition of a PyTree is “a tree-like structure built out of container-like Python objects. Classes are considered container-like if they are in the PyTree registry”.

By default, the PyTree registry includes the class `list`. `tuple`, and `dict`. Any other object not in the registry will be considered a leaf in the PyTree structure. 

