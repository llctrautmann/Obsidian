---
title: Matrix Tricks
date:
  - 12-06-2024
time: 18:43
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
# Cool Matrix tricks

1. get the sum for all columns: 

$$
\mathbf{1}_N^{\top} \mathbf{X}=\left(\begin{array}{lll}
\sum_n x_{n 1} & \cdots & \sum_n x_{n D}
\end{array}\right)
$$
just multiply with a 1 x N vector of ones 

2. get the sum for all rows 

Multiply (nachgestellt) with a D x 1 vector of 1s. 

$$
\mathbf{X} 1_D=\left(\begin{array}{c}
\sum_d x_{1 d} \\
\vdots \\
\sum_d x_{N d}
\end{array}\right)
$$
combine both to sum all values in the matrix 

$$
\mathbf{1}_N^{\top} \mathbf{X} \mathbf{1}_D=\sum_{i j} X_{i j}
$$

This also allows the calculation of means: 

total matrix: 

$$
\bar{x}=\frac{1}{N D} \mathbf{1}_N^{\top} \mathbf{X} \mathbf{1}_D
$$


column means

$$
\overline{\boldsymbol{x}}^{\top}=\frac{1}{N} \mathbf{1}_N^{\top} \mathbf{X}
$$

row means

$$
\overline{\boldsymbol{x}}^{\top}=\frac{1}{D} \mathbf{X}\mathbf{1}_D
$$


# Scaling rows and columns of a matrix
This is relevant wrt. [[Eigenvalue decomposition|EVD]]: Scaling works with diagonal mat 


# Standardize in Linear Algebra

$$
\operatorname{standardize}(\mathbf{X})=\left(\mathbf{X}-\mathbf{1}_N \boldsymbol{\mu}^T\right) \operatorname{diag}(\boldsymbol{\sigma})^{-1}
$$
