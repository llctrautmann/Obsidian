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
type: Theorem
🍙: いや
formula: "$\\|\\cdot\\|: V & \\rightarrow \\mathbb{R}$"
aliases:
  - norm
  - norms
modified: 2024-06-12
---
# Norms in Linear Algebra
## Definition
A norm is a function onto the real line. Hence, a norm is a special case of [[Linear Maps]] from a vector space $V$ onto $\mathbb{R}^1$. Norms are principally related to length in the special case of 2D Euclidean space [^4] (see: [[Generalised Euclidean Space]]). They are also closely related to [[Metrics]] as outlined below. 


**Definition 3.1 (Norm)**. A norm on a vector space $V$ is a function

$$
\begin{aligned}
\|\cdot\|: V & \rightarrow \mathbb{R}, \\
x & \mapsto\|x\|,
\end{aligned}
$$

## Conditions
Norms assigns each vector $x$ its length $\|x\| \in \mathbb{R}$, such that for all $\lambda \in \mathbb{R}$ and $x, y \in V$ the following hold:

- Absolutely homogeneous: $\|\lambda x\|=|\lambda|\|x\|$
- [[Triangle inequality]]: $\|\boldsymbol{x}+\boldsymbol{y}\| \leqslant\|\boldsymbol{x}\|+\|\boldsymbol{y}\|$ [^2]
- Non-negativity: $\|x\| \geqslant 0$ 
- Definiteness: $\|x\|=0 \Longleftrightarrow x=0$


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

Note that the l1- and l2-norms are special cases of the $p$-norm, and the $x$-norm is the limit of the $p$-norm as $p$ tends to infinity. We require $p \geq 1$ for the general definition of the $p$-norm because the triangle inequality fails to hold if $p<1$. 

Here's a fun fact: for any given finite-dimensional vector space $V$, all norms on $V$ are equivalent in the sense that for two norms $\|\cdot\|_A,\|\cdot\|_B$, there exist constants $\alpha, \beta>0$ such that
$$
\alpha\|\mathbf{x}\|_A \leq\|\mathbf{x}\|_B \leq \beta\|\mathbf{x}\|_A
$$
for all $\mathrm{x} \in V$. Therefore convergence in one norm implies convergence in any other norm. This rule may not apply in infinite-dimensional vector spaces such as function spaces, though.

## Norms and Metrics
The rules for norms and the rules for metrics are very close and hence any norm also induces a metric [^3]

## Matrix Norms
Assume $f(x) = \mathbf{A}\mathbf{x}$ as we do normally. The norm of $\mathbf{A}$ is then the maximum amount that $\mathbf{A}$ can stretch any unit-norm input[^1]. 
	- $\|\mathbf{A}\|_p=\max _{\boldsymbol{x} \neq 0} \frac{\|\mathbf{A} \boldsymbol{x}\|_p}{\|\boldsymbol{x}\|_p}=\max _{\|\boldsymbol{x}\|=1}\|\mathbf{A} \boldsymbol{x}\|_p$ 

In most cases I will encounter that $p=2$ which leads to the following specific norm: 
	- $\|\mathbf{A}\|_2=\sqrt{\lambda_{\max }\left(\mathbf{A}^{\top} \mathbf{A}\right)}=\max _i \sigma_i$ with $\lambda_{max}(\mathbf{M})=\text{largest eigevalue of M}$ and $\sigma_{i}$ equal to the i-th singular value 


# Footnotes

[^1]: [[murphy2022.pdf#page=263&selection=288,2,300,32&color=yellow|murphy2022, p.233]] 
[^2]: [[deisenroth2020.pdf#page=77&selection=203,0,205,37|deisenroth2020, p.71]] 
[^3]: [[Thomas2018.pdf#page=10&selection=104,0,105,72&color=yellow|Thomas2018, p.10]] 
[^4]: [[murphy2022.pdf#page=262&selection=360,0,370,55&color=yellow|murphy2022, p.232]] 