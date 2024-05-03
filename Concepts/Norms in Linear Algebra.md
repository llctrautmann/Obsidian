---
title: Norms in Linear Algebra
date:
  - 24-04-2024
time: 22:58
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: 7
status: Incomplete
modified: 2024-05-03
---
# Norms in Linear Algebra
A norm is a mapping from a vector space $V$ onto $\mathbb{R}^1$. 


**Definition 3.1 (Norm)**. A norm on a vector space $V$ is a function

$$
\begin{aligned}
\|\cdot\|: V & \rightarrow \mathbb{R}, \\
x & \mapsto\|x\|,
\end{aligned}
$$

which assigns each vector $x$ its length $\|x\| \in \mathbb{R}$, such that for all $\lambda \in \mathbb{R}$ and $x, y \in V$ the following hold:

- Absolutely homogeneous: $\|\lambda x\|=|\lambda|\|x\|$
- Triangle inequality: $\|\boldsymbol{x}+\boldsymbol{y}\| \leqslant\|\boldsymbol{x}\|+\|\boldsymbol{y}\|$
- Positive definite: $\|x\| \geqslant 0$ and $\|x\|=0 \Longleftrightarrow x=0$

In geometric terms, the triangle inequality states that for any triangle, the sum of the lengths of any two sides must be greater than or equal to the length of the remaining side; ([[deisenroth2020.pdf]] et al., 2020, p. 71) 

### Common Norms
1. Manhatten Norm: $$
\|x\|_1:=\sum_{i=1}^n\left|x_i\right|
$$
2. Euclidean Norm: 
$$
\|\boldsymbol{x}\|_2:=\sqrt{\sum_{i=1}^n x_i^2}=\sqrt{\boldsymbol{x}^{\top} \boldsymbol{x}}
$$