---
title: "Defining Spaces in Linear Algebra: Span, Rank, Basis"
date:
  - 17-05-2024
time: 22:23
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-17
---
# Defining Spaces in Linear Algebra: Span, Rank, Basis
## Span
Consider [[Vector Spaces]]

$$\large\tag{1}
(\mathcal{V},+, \cdot)
$$

and a set of vectors $\mathcal{A}=\{x_{1}, x_{2},\dots, x_{n}\} \subseteq (\mathcal{V},+, \cdot)$. If every vector $\operatorname{v} \in \mathcal{V}$ can be expressed as a linear combination of $\{x_{1}, x_{2},\dots, x_{n}\}$, $\mathcal{A}$ is called a __generating set__ of $\mathcal{V}$. The set of all linear combinations of vectors in $\mathcal{A}$ is called the __span__. 

The notation for a vectors space is
$$
V=\operatorname{span}[\mathcal{A}]
$$
Generating sets are sets of vectors that span vector (sub)spaces, i.e., every vector can be represented as a linear combination of the vectors in the generating set. 


## Basis

**Basis**: set of vectors with which we can represent every vector in the vector space by adding them together and scaling them. Alternatively, it is correct to say: A basis is a minimal generating set of maximal linearly independent set of vectors.

Think:

