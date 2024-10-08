---
title: Kronecker Product
date:
  - 10-06-2024
time: 16:41
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
# Kronecker Product
## Definition
If $\mathbf{A}$ is an $m \times n$ matrix and $\mathbf{B}$ is a $p \times q$ matrix, then the Kronecker product $\mathbf{A} \otimes \mathbf{B}$ is the $p m \times q n$ block matrix:
$$\mathbf{A} \otimes \mathbf{B}=\left[\begin{array}{ccc}a_{11} \mathbf{B} & \cdots & a_{1 n} \mathbf{B} \\ \vdots & \ddots & \vdots \\ a_{m 1} \mathbf{B} & \cdots & a_{m n} \mathbf{B}\end{array}\right]$$
more explicitly:
$$
\mathbf{A} \otimes \mathbf{B}=\left[\begin{array}{cccccccccc}
a_{11} b_{11} & a_{11} b_{12} & \cdots & a_{11} b_{1 q} & \cdots & \cdots & a_{1 n} b_{11} & a_{1 n} b_{12} & \cdots & a_{1 n} b_{1 q} \\
a_{11} b_{21} & a_{11} b_{22} & \cdots & a_{11} b_{2 q} & \cdots & \cdots & a_{1 n} b_{21} & a_{1 n} b_{22} & \cdots & a_{1 n} b_{2 q} \\
\vdots & \vdots & \ddots & \vdots & & & \vdots & \vdots & \ddots & \vdots \\
a_{11} b_{p 1} & a_{11} b_{p 2} & \cdots & a_{11} b_{p q} & \cdots & \cdots & a_{1 n} b_{p 1} & a_{1 n} b_{p 2} & \cdots & a_{1 n} b_{p q} \\
\vdots & \vdots & & \vdots & \ddots & & \vdots & \vdots & & \vdots \\
\vdots & \vdots & & \vdots & & \ddots & \vdots & \vdots & & \vdots \\
a_{m 1} b_{11} & a_{m 1} b_{12} & \cdots & a_{m 1} b_{1 q} & \cdots & \cdots & a_{m n} b_{11} & a_{m n} b_{12} & \cdots & a_{m n} b_{1 q} \\
a_{m 1} b_{21} & a_{m 1} b_{22} & \cdots & a_{m 1} b_{2 q} & \cdots & \cdots & a_{m n} b_{21} & a_{m n} b_{22} & \cdots & a_{m n} b_{2 q} \\
\vdots & \vdots & \ddots & \vdots & & & \vdots & \vdots & \ddots & \vdots \\
a_{m 1} b_{p 1} & a_{m 1} b_{p 2} & \cdots & a_{m 1} b_{p q} & \cdots & \cdots & a_{m n} b_{p 1} & a_{m n} b_{p 2} & \cdots & a_{m n} b_{p q}
\end{array}\right] .
$$

## Noteworthy
- Here are some useful identities[^1]: 
$$\large\tag{1}
\begin{aligned}
(\mathbf{A} \otimes \mathbf{B})^{-1} & =\mathbf{A}^{-1} \otimes \mathbf{B}^{-1} \\
(\mathbf{A} \otimes \mathbf{B}) \operatorname{vec}(\mathbf{C}) & =\operatorname{vec}\left(\mathbf{B C A ^ { \top } )}\right.
\end{aligned}
$$
this is also being used in the probabilisitic numerics book
[^1]: vec(M) stacks the columns of M