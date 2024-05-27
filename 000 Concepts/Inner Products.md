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
modified: 2024-05-27
---
# Inner Products
## Purpose
Inner products allow for the introduction of intuitive geometrical concepts, such as the length of a vector and the angle or distance between two vectors. 


## Definition
Inner products are defined on [[Vector Spaces]] and constitute a function - more specifically a bilinear mapping - from the vector space onto the real line. 


$(1)$ Is the definition of the generalised inner product. 

$$\large\tag{1}
\langle\cdot, \cdot\rangle: V \times V \rightarrow \mathbb{R}
$$

`So its a function: with two inputs and one scalar output.`

The inner product is just a bilinear mapping or function that requires certain condition (see next point) to be met.

## Conditions
Firstly, the bilinear map must adhere to the fundamental axioms of vector spaces: addition and multiplication.

$$\large\tag{2}
\begin{aligned}
& \Omega(\lambda x+\psi \boldsymbol{y}, \boldsymbol{z})=\lambda \Omega(\boldsymbol{x}, \boldsymbol{z})+\psi \Omega(\boldsymbol{y}, \boldsymbol{z}) \\
& \Omega(\boldsymbol{x}, \lambda \boldsymbol{y}+\psi \boldsymbol{z})=\lambda \Omega(\boldsymbol{x}, \boldsymbol{y})+\psi \Omega(\boldsymbol{x}, \boldsymbol{z}) .
\end{aligned}
$$

$(2)$ shows that, the core axioms of addition and multiplication defined for [[Vector Spaces]] hold. 

If these two conditions are met, additionally the following conditions need to be met:

1. $\langle\mathbf{x}, \mathbf{x}\rangle \geq 0$, with equality if and only if $\mathbf{x}=\mathbf{0}$
2. Linearity in the first slot: $$\langle\mathbf{x}+\mathbf{y}, \mathbf{z}\rangle=\langle\mathbf{x}, \mathbf{z}\rangle+\langle\mathbf{y}, \mathbf{z}\rangle \quad \text{and} \quad \langle\alpha \mathbf{x}, \mathbf{y}\rangle=\alpha\langle\mathbf{x}, \mathbf{y}\rangle$$

3. Symmetry
$$
\langle\mathbf{x}, \mathbf{y}\rangle=\langle\mathbf{y}, \mathbf{x}\rangle
$$

## Noteworthy
### Inner Products Inducing Norms
Inner products induce [norms](Norms%20in%20Linear%20Algebra), which induce [[Metrics]]. So a [[Vector Spaces]] with an inner product, has a norm (measure of length) and has a metric (measure of distance). So a inner product space, is a normed space, is a metric space.


$$\large\tag{2}
\|\mathbf{x}\|=\sqrt{\langle\mathbf{x}, \mathbf{x}\rangle}
$$

Hence, there exists a deep connection between [norms](Norms%20in%20Linear%20Algebra), [[Metrics]] and [[Inner Products]]. A major purpose of inner products is to determine whether vectors are orthogonal to each other. So there is also a connection to [[orthogonality]].


# References
> [!PDF|yellow] [[Thomas2018.pdf#page=11&selection=52,1,54,37&color=yellow|Thomas2018, p.11]]
> > Therefore any inner product space is also a normed space (and hence also a metric space)
> 
> 