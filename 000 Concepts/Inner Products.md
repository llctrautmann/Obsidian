---
title: Inner Products
date:
  - 22-05-2024
time: 17:57
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: Concept
formula: "$\\langle\\cdot, \\cdot\\rangle: V \\times V \\rightarrow \\mathbb{R}$"
🍙: いや
modified: 2024-05-25
---
# Inner Products
Inner products are defined on [[Vector Spaces]] and constitute a function from the vector space onto the real line. There exists a deep connection between [norms](Norms%20in%20Linear%20Algebra), [[Metrics]] and [[Inner Products]]. 


$$\large\tag{1}
\langle\cdot, \cdot\rangle: V \times V \rightarrow \mathbb{R}
$$
## Conditions
1. $\langle\mathbf{x}, \mathbf{x}\rangle \geq 0$, with equality if and only if $\mathbf{x}=\mathbf{0}$
2. Linearity in the first slot: $$\langle\mathbf{x}+\mathbf{y}, \mathbf{z}\rangle=\langle\mathbf{x}, \mathbf{z}\rangle+\langle\mathbf{y}, \mathbf{z}\rangle \quad \text{and} \quad \langle\alpha \mathbf{x}, \mathbf{y}\rangle=\alpha\langle\mathbf{x}, \mathbf{y}\rangle$$

3. Symmetry
$$
\langle\mathbf{x}, \mathbf{y}\rangle=\langle\mathbf{y}, \mathbf{x}\rangle
$$

## Inner Products and Norms
Inner products induce [norms](Norms%20in%20Linear%20Algebra), which induce [[Metrics]]. So a [[Vector Spaces]] with an inner product, has a norm (measure of length) and has a metric (measure of distance). 

So a inner product space, is a normed space, is a metric space.

## Inner Product Inducing Norms
Any inner product induces a norm (measure of length), 

$$\large\tag{2}
\|\mathbf{x}\|=\sqrt{\langle\mathbf{x}, \mathbf{x}\rangle}
$$



# References
> [!PDF|yellow] [[Thomas2018.pdf#page=11&selection=52,1,54,37&color=yellow|Thomas2018, p.11]]
> > Therefore any inner product space is also a normed space (and hence also a metric space)
> 
> 