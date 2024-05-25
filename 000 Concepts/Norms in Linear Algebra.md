---
title: Norms in Linear Algebra
date:
  - 24-04-2024
time: 22:58
author: Luca Trautmann
tags:
  - "#LinAlg"
  - AnalyticGeometry
series: Linear Algebra
chapter: 0
status: Complete
modified: 2024-05-25
type: Theorem
related: "[[Metrics]]"
---
# Norms in Linear Algebra
A norm is a function onto the real line. Hence, a norm is a special case of [[Linear Maps]] from a vector space $V$ onto $\mathbb{R}^1$. Norms are principally related to length in the special case of 2D Euclidean space (see: [[Generalised Euclidean Space]]). They are also closely related to [[Metrics]] as outlined below . induces:: [[Metrics]]


**Definition 3.1 (Norm)**. A norm on a vector space $V$ is a function

$$
\begin{aligned}
\|\cdot\|: V & \rightarrow \mathbb{R}, \\
x & \mapsto\|x\|,
\end{aligned}
$$

which assigns each vector $x$ its length $\|x\| \in \mathbb{R}$, such that for all $\lambda \in \mathbb{R}$ and $x, y \in V$ the following hold:

- Absolutely homogeneous: $\|\lambda x\|=|\lambda|\|x\|$
- [[Triangle inequality]]: $\|\boldsymbol{x}+\boldsymbol{y}\| \leqslant\|\boldsymbol{x}\|+\|\boldsymbol{y}\|$
- Positive definite: $\|x\| \geqslant 0$ and $\|x\|=0 \Longleftrightarrow x=0$


## Common Norms
1. Manhattan Norm: $$
\|x\|_1:=\sum_{i=1}^n\left|x_i\right|
$$
2. Euclidean Norm: 
$$
\|\boldsymbol{x}\|_2:=\sqrt{\sum_{i=1}^n x_i^2}=\sqrt{\boldsymbol{x}^{\top} \boldsymbol{x}}
$$
3. P-Norm
$$
\|\mathbf{x}\|_p=\left(\sum_{i=1}^n\left|x_i\right|^p\right)^{\frac{1}{p}} \quad(p \geq 1)
$$

4. $\infty$-Norm
$$
\|\mathbf{x}\|_{\infty}=\max _{1 \leq i \leq n}\left|x_i\right|
$$

Note that the 1 - and 2 -norms are special cases of the $p$-norm, and the $x$-norm is the limit of the $p$-norm as $p$ tends to infinity. We require $p \geq 1$ for the general definition of the $p$-norm because the triangle inequality fails to hold if $p<1$. (Try to find a counterexample!)

Here's a fun fact: for any given finite-dimensional vector space $V$, all norms on $V$ are equivalent in the sense that for two norms $\|\cdot\|_A,\|\cdot\|_B$, there exist constants $\alpha, \beta>0$ such that
$$
\alpha\|\mathbf{x}\|_A \leq\|\mathbf{x}\|_B \leq \beta\|\mathbf{x}\|_A
$$
for all $\mathrm{x} \in V$. Therefore convergence in one norm implies convergence in any other norm. This rule may not apply in infinite-dimensional vector spaces such as function spaces, though.

# References

> ([[deisenroth2020.pdf#page=77&selection=203,0,205,37|deisenroth2020, p.71]])
> In geometric terms, the triangle inequality states that for any triangle, the sum of the lengths of any two sides must be greater than or equal to the length of the remaining side; 

> [!PDF|yellow] [[Thomas2018.pdf#page=10&selection=104,0,105,72&color=yellow|Thomas2018, p.10]]
> > One can verify that the axioms for metrics are satisfied under this definition and follow directly from the axioms for norms. Therefore any normed space is also a metric space.



Example:: [[Metrics]]
