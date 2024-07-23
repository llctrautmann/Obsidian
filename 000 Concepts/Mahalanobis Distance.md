---
title: Mahalanobis Distance
date:
  - 23-07-2024
time: 10:30
author: Luca Trautmann
tags:
  - ProbTheory
series: Probability Theory
level: "0"
🍙: いや
type: 
formula: 
aliases: 
Docstring:
  - The Mahalanobis Distance allows for a geometric view on gaussians. The eigenvalue decomposition shows that the eigenvalue determines the elongation while the eigenvalues give the direction of the ellipses.
modified: 2024-07-23
---
# Mahalanobis Distance
## Introduction
We attempt to gain some insights into the geometric shape of the Gaussian pdf in multiple dimensions. 

## Definition
The $\log$ probability at a specific point $\boldsymbol{y}$ is given by
$$
\log p(\boldsymbol{y} \mid \boldsymbol{\mu}, \boldsymbol{\Sigma})=-\frac{1}{2}(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{\Sigma}^{-1}(\boldsymbol{y}-\boldsymbol{\mu})+\text { const }
$$

The dependence on $\boldsymbol{y}$ can be expressed in terms of the Mahalanobis distance $\Delta$ between $\boldsymbol{y}$ and $\boldsymbol{\mu}$, whose square is defined as follows:
$$
\Delta^2 \triangleq(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{\Sigma}^{-1}(\boldsymbol{y}-\boldsymbol{\mu})
$$

Thus contours of constant (log) probability are equivalent to contours of constant Mahalanobis distance.

To gain insight into the contours of constant Mahalanobis distance, we exploit the fact that $\boldsymbol{\Sigma}$, and hence $\boldsymbol{\Lambda}=\boldsymbol{\Sigma}^{-1}$, are both positive definite matrices (by assumption). Consider the following [[Eigenvalue decomposition]] of $\boldsymbol{\Sigma}$ :
$$
\boldsymbol{\Sigma}=\sum_{d=1}^D \lambda_d \boldsymbol{u}_d \boldsymbol{u}_d^{\top}
$$

We can similarly write
$$
\boldsymbol{\Sigma}^{-1}=\sum_{d=1}^D \frac{1}{\lambda_d} \boldsymbol{u}_d \boldsymbol{u}_d^{\top}
$$

Let us define $z_d \triangleq \boldsymbol{u}_d^{\top}(\boldsymbol{y}-\boldsymbol{\mu})$, so $\boldsymbol{z}=\mathbf{U}(\boldsymbol{y}-\boldsymbol{\mu})$. Then we can rewrite the Mahalanobis distance as follows:
$$
\begin{aligned}
(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{\Sigma}^{-1}(\boldsymbol{y}-\boldsymbol{\mu}) & =(\boldsymbol{y}-\boldsymbol{\mu})^{\top}\left(\sum_{d=1}^D \frac{1}{\lambda_d} \boldsymbol{u}_d \boldsymbol{u}_d^{\top}\right)(\boldsymbol{y}-\boldsymbol{\mu}) \\
& =\sum_{d=1}^D \frac{1}{\lambda_d}(\boldsymbol{y}-\boldsymbol{\mu})^{\top} \boldsymbol{u}_d \boldsymbol{u}_d^{\top}(\boldsymbol{y}-\boldsymbol{\mu})=\sum_{d=1}^D \frac{z_d^2}{\lambda_d}
\end{aligned}
$$

This means we can interpret the Mahalanobis distance as Euclidean distance in a new coordinate frame $\boldsymbol{z}$ in which we rotate $\boldsymbol{y}$ by $\mathbf{U}$ and scale by $\boldsymbol{\Lambda}$.

For example, in 2 d , let us consider the set of points $\left(z_1, z_2\right)$ that satisfy this equation:
$$
\frac{z_1^2}{\lambda_1}+\frac{z_2^2}{\lambda_2}=r
$$

Since these points have the same Mahalanobis distance, they correspond to points of equal probability. Hence we see that the contours of equal probability density of a 2 d Gaussian lie along ellipses. This is illustrated in Figure 7.6. The eigenvectors determine the orientation of the ellipse, and the eigenvalues determine how elongated it is.

## Noteworthy
- There is a connection here to the [[Eigenvalue decomposition]]. 
- 