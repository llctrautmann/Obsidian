---
title: Vectors Subspaces
date:
  - 12-05-2024
time: 14:47
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-12
---
# Vectors Subspaces

Subspaces are more limited spaces within existing vectors spaces. For example, if I transform a larger space into a lower dimensional space, the [[Null Space]] is the space that contain all the vectors that are $\mathbf{0}$ in the new vector space. 

$$
S \subseteq V
$$

## Rules for Subspaces

1. Must contain $\mathbf{0}$ 

`This is a direct consequence of` [[Vector Spaces#Additive Identity]]`needing to contain the zero element so that` $x+0=x$ `holds`.

2. $S$ needs to be closed under addition. 

`This relates to the fundamental principle of an algebra` [[Linear Algebra#What is an algebra?]]. `We need to stay the same element.` 

3. Closed under scalar multiplication: 
$$\mathbf{x} \in S, \alpha \in \mathbb{R}$$ therefore. $$\alpha \mathbf{x} \in S$$

`same as 2.`  