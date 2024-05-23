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
formula: 
🍙: いや
modified: 2024-05-23
---
# Inner Products
Inner products are defined on [[Vector Spaces]] and constitute a function from the vector space onto the real line. There exists a deep connection between [norms](Norms%20in%20Linear%20Algebra), [[Metrics]] and [[Inner Products]]. 


$$\large\tag{1}
\langle\cdot, \cdot\rangle: V \times V \rightarrow \mathbb{R}
$$

1. $\langle\mathbf{x}, \mathbf{x}\rangle \geq 0$, with equality if and only if $\mathbf{x}=\mathbf{0}$
2. Linearity in the first slot: $\langle\mathbf{x}+\mathbf{y}, \mathbf{z}\rangle=\langle\mathbf{x}, \mathbf{z}\rangle+\langle\mathbf{y}, \mathbf{z}\rangle$ and $\langle\alpha \mathbf{x}, \mathbf{y}\rangle=\alpha\langle\mathbf{x}, \mathbf{y}\rangle$
3. Sy
$$
\langle\mathbf{x}, \mathbf{y}\rangle=\langle\mathbf{y}, \mathbf{x}\rangle
$$
