---
title: Matrix Definitions
date:
  - 05-02-2024
time: 10:13
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 0
modified: 2024-05-14
---
# Matrix: Definition

## What is a Linear Map
With $m, n \in \mathbb{N}$ a real-valued $(m, n)$ matrix $A$ is an $m \cdot n$-tuple of elements $a_{i j}, i=1, \ldots, m, j=1, \ldots, n$, which is ordered according to a rectangular scheme consisting of $m$ rows and $n$ columns:
$$
\boldsymbol{A}=\left[\begin{array}{cccc}
a_{11} & a_{12} & \cdots & a_{1 n} \\
a_{21} & a_{22} & \cdots & a_{2 n} \\
\vdots & \vdots & & \vdots \\
a_{m 1} & a_{m 2} & \cdots & a_{m n}
\end{array}\right], \quad a_{i j} \in \mathbb{R} .
$$

By convention $(1, n)$-matrices are called rows and $(m, 1)$-matrices are called columns. These special matrices are also called row/column vectors.


## Basic Algebra Actions: Add and Multiply
Summing is conducted element-wise:

$$\boldsymbol{A}+\boldsymbol{B}:=\left[\begin{array}{ccc}a_{11}+b_{11} & \cdots & a_{1 n}+b_{1 n} \\ \vdots & & \vdots \\ a_{m 1}+b_{m 1} & \cdots & a_{m n}+b_{m n}\end{array}\right] \in \mathbb{R}^{m \times n}$$

Multiplication works by multiplying the rows of A with the Columns of B and summing the result ([[Inner Products]]). Indicated by the following expression: 
$$c_{i j}=\sum_{l=1}^n a_{i l} b_{l j}, \quad i=1, \ldots, m, \quad j=1, \ldots, k$$
The only requirement here is $\underbrace{\boldsymbol{A}}_{n \times k} \underbrace{B}_{k \times m}=\underbrace{C}_{n \times m}$. Element-wise multiplication is known as the _Hadamard product_. Matrix multiplication is not commutative. 



## Identity Matrix
Definition 2.2 (Identity Matrix). In $\mathbb{R}^{n \times n}$, we define the identity matrix

$$
\boldsymbol{I}_n:=\left[\begin{array}{cccccc}
1 & 0 & \cdots & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 1 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 0 & \cdots & 1
\end{array}\right] \in \mathbb{R}^{n \times n}
$$

as the $n \times n$-matrix containing 1 on the diagonal and 0 everywhere else.

## Properties of matrices

- _Associativity_:
$$
\forall \boldsymbol{A} \in \mathbb{R}^{m \times n}, \boldsymbol{B} \in \mathbb{R}^{n \times p}, \boldsymbol{C} \in \mathbb{R}^{p \times q}:(\boldsymbol{A B}) \boldsymbol{C}=\boldsymbol{A}(\boldsymbol{B} \boldsymbol{C})
$$
- _Distributivity_:
$$
\begin{aligned}
\forall \boldsymbol{A}, \boldsymbol{B} \in \mathbb{R}^{m \times n}, \boldsymbol{C}, \boldsymbol{D} \in \mathbb{R}^{n \times p}&:(\boldsymbol{A}+\boldsymbol{B}) \boldsymbol{C}=\boldsymbol{A} \boldsymbol{C}+\boldsymbol{B} \boldsymbol{C} \\
&\boldsymbol{A}(\boldsymbol{C}+\boldsymbol{D})=\boldsymbol{A} \boldsymbol{C}+\boldsymbol{A} \boldsymbol{D} \\
\end{aligned}
$$
- Multiplication with the identity matrix:
$$
\forall \boldsymbol{A} \in \mathbb{R}^{m \times n}: \boldsymbol{I}_m \boldsymbol{A}=\boldsymbol{A} \boldsymbol{I}_n=\boldsymbol{A}
$$

Note that $\boldsymbol{I}_m \neq \boldsymbol{I}_n$ for $m \neq n$.

## Inverse and Transpose








