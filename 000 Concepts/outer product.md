---
title: outer product
date:
  - 12-06-2024
time: 18:32
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: 
aliases: 
modified: 2024-06-12
---
# outer product
Given vectors $\boldsymbol{x} \in \mathbb{R}^m, y \in \mathbb{R}^n$ (they no longer have to be the same size), $x y^{\prime}$ is called the outer product of the vectors. It is a matrix whose entries are given by $\left(x y^{\top}\right)_{i j}=x_i y_j$, i.e.,
$$
x y^{\top} \in \mathbb{R}^{m \times n}=\left[\begin{array}{cccc}
x_1 y_1 & x_1 y_2 & \cdots & x_1 y_n \\
x_2 y_1 & x_2 y_2 & \cdots & x_2 y_n \\
\vdots & \vdots & \ddots & \vdots \\
x_m y_1 & x_m y_2 & \cdots & x_m y_n
\end{array}\right] .
$$

This is relevant is [[Matrix-Matrix Multiplication]] and helps me in understanding [[Eigenvalue decomposition|EVD]] [^1]
# Footnotes

[^1]: Note: The scaling interpretation makes understanding why $\mathbf{A U}=\mathbf{U} \Lambda$ is necessary.