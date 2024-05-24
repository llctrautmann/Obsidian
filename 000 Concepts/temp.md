---
title: temp
date:
  - 24-05-2024
time: 23:48
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: 
formula: 
🍙: いや
modified: 2024-05-25
---
# temp

## Matrix Multiplication

the product of two matrices is another matrix

$$\large\tag{1}
\mathbf{C}=\mathbf{A} \mathbf{B} \in \mathbb{R}^{m \times p}
$$
where
$$\large\tag{2}
C_{i j}=\sum_{k=1}^n A_{i k} B_{k j}
$$

> [!PDF|yellow] [[murphy2022.pdf#page=270&selection=172,0,180,1&color=yellow|murphy2022, p.240]]
> > Note that in order for the matrix product to exist, the number of columns in A must equal the number of rows in B.

matmul is associative and distributiv but ususally not commutative (ab != ba)

## Vec Vec Mul

$$\large\tag{3}
\langle\boldsymbol{x}, \boldsymbol{y}\rangle \triangleq \boldsymbol{x}^{\top} \boldsymbol{y}=\sum_{i=1}^n x_i y_i
$$

the outer product is in contrast to the [[Inner Products]] and produces a matrix. [[Inner Products]] produce scalars. 

$$\large\tag{4}
\boldsymbol{x} \boldsymbol{y}^{\top} \in \mathbb{R}^{m \times n}=\left[\begin{array}{cccc}
x_1 y_1 & x_1 y_2 & \cdots & x_1 y_n \\
x_2 y_1 & x_2 y_2 & \cdots & x_2 y_n \\
\vdots & \vdots & \ddots & \vdots \\
x_m y_1 & x_m y_2 & \cdots & x_m y_n
\end{array}\right] .
$$


# Matrix-vector products

Given a matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$ and a vector $\boldsymbol{x} \in \mathbb{R}^n$, their product is a vector $\boldsymbol{y}=\mathbf{A} \boldsymbol{x} \in \mathbb{R}^m$. There are a couple of ways of looking at matrix-vector multiplication, and we will look at them both.
If we write $\mathbf{A}$ by rows, then we can express $\boldsymbol{y}=\mathbf{A} \boldsymbol{x}$ as follows:
$$
\boldsymbol{y}=\mathbf{A} \boldsymbol{x}=\left[\begin{array}{ccc}
- & \boldsymbol{a}_1^{\top} & - \\
- & \boldsymbol{a}_2^{\top} & - \\
& \vdots & \\
- & \boldsymbol{a}_m^{\top} & -
\end{array}\right] \boldsymbol{x}=\left[\begin{array}{c}
\boldsymbol{a}_1^{\top} \boldsymbol{x} \\
\boldsymbol{a}_2^{\top} \boldsymbol{x} \\
\vdots \\
\boldsymbol{a}_m^{\top} \boldsymbol{x}
\end{array}\right]
$$

In other words, the $i$ th entry of $\boldsymbol{y}$ is equal to the inner product of the $i$ th row of $\mathbf{A}$ and $\boldsymbol{x}, y_i=\boldsymbol{a}_i^{\top} \boldsymbol{x}$. Alternatively, let's write $\mathbf{A}$ in column form. In this case we see that
$$
\boldsymbol{y}=\mathbf{A} \boldsymbol{x}=\left[\begin{array}{cccc}
\mid & \mid & & \mid \\
\boldsymbol{a}_1 & \boldsymbol{a}_2 & \cdots & \boldsymbol{a}_n \\
\mid & \mid & & \mid
\end{array}\right]\left[\begin{array}{c}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{array}\right]=\left[\begin{array}{c}
\mid \\
\boldsymbol{a}_1 \\
\mid
\end{array}\right] x_1+\left[\begin{array}{c}
\mid \\
\boldsymbol{a}_2 \\
\mid
\end{array}\right] x_2+\ldots+\left[\begin{array}{c}
\mid \\
\boldsymbol{a}_n \\
\mid
\end{array}\right] x_n .
$$

In other words, $\boldsymbol{y}$ is a linear combination of the columns of $\mathbf{A}$, where the coefficients of the linear combination are given by the entries of $\boldsymbol{x}$. We can view the columns of $\mathbf{A}$ as a set of basis vectors defining a linear subspace. We can construct vectors in this subspace by taking linear combinations of the basis vectors. See Section 7.1.2 for details.

I reference this also in the note on [[Geometry of Linear Algebra]]


# Matrix Matrix Products


# Cool Matrix tricks

get the sum for all columns: 

$$
\mathbf{1}_N^{\top} \mathbf{X}=\left(\begin{array}{lll}
\sum_n x_{n 1} & \cdots & \sum_n x_{n D}
\end{array}\right)
$$
just multiply with a 1 x N vector of ones 

get the sum for all rows 

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
`turn this into a note and add a reference in the note that describes the properties of specific linear maps`
Diagonal Matrices allow us to sc

1 1    3 0   3 3
1 0    0 3   3 0 `check for non square matrices tomorrow` 


# Standardize in Linear Algebra

$$
\operatorname{standardize}(\mathbf{X})=\left(\mathbf{X}-\mathbf{1}_N \boldsymbol{\mu}^T\right) \operatorname{diag}(\boldsymbol{\sigma})^{-1}
$$




