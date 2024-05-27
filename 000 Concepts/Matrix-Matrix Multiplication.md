---
title: Matrix-Matrix Multiplication
date:
  - 27-05-2024
time: 20:32
author: Luca Trautmann
tags:
  - LinAlg
  - "#Process"
series: Linear Algebra
🍙: いや
type: Process
formula: 
aliases: 
modified: 2024-05-27
---
# Matrix-Matrix Multiplication
The product of two matrices $\mathbf{A} \in \mathbb{R}^{m \times n}$ and $\mathbf{B} \in \mathbb{R}^{n \times p}$ is the matrix
$$
\mathbf{C}=\mathbf{A B} \in \mathbb{R}^{m \times p},
$$
where
$$
C_{i j}=\sum_{k=1}^n A_{i k} B_{k j} .
$$

- Matrix multiplication is associative: $(\mathbf{A B}) \mathbf{C}=\mathbf{A}(\mathbf{B C})$.
- Matrix multiplication is distributive: $\mathbf{A}(\mathbf{B}+\mathbf{C})=\mathbf{A B}+\mathbf{A C}$.
- Matrix multiplication is, in general, not commutative; that is, it can be the case that $\mathbf{A B} \neq \mathbf{B A}$.


There are four different ways of looking at matrix-matrix multiplication contained in the above statement and depending on the situation it is useful to look at a problem form either perspective. 

## Vector-Vector / Inner-Products
$$\large\tag{1}
\mathbf{C}=\mathbf{A B}=\left[\begin{array}{ccc}
- & \boldsymbol{a}_1^{\top} & - \\
- & \boldsymbol{a}_2^{\top} & - \\
& \vdots & \\
- & \boldsymbol{a}_m^{\top} & -
\end{array}\right]\left[\begin{array}{cccc}
\mid & \mid & & \mid \\
\boldsymbol{b}_1 & \boldsymbol{b}_2 & \cdots & \boldsymbol{b}_p \\
\mid & \mid & & \mid
\end{array}\right]=\left[\begin{array}{cccc}
\boldsymbol{a}_1^{\top} \boldsymbol{b}_1 & \boldsymbol{a}_1^{\top} \boldsymbol{b}_2 & \cdots & \boldsymbol{a}_1^{\top} b_p \\
\boldsymbol{a}_2 \boldsymbol{b}_1 & \boldsymbol{a}_2^{\top} b_2 & \cdots & \boldsymbol{a}_2^{\top} b_p \\
\vdots & \vdots & \ddots & \vdots \\
\boldsymbol{a}_m^{\top} \boldsymbol{b}_1 & \boldsymbol{a}_m^{\top} b_2 & \cdots & \boldsymbol{a}_m^{\top} b_p
\end{array}\right]
$$
## Outer-Products (Scaling)

$$\large\tag{2} 
\mathbf{C}=\mathbf{A B}=\left[\begin{array}{cccc}
\mid & \mid & & \mid \\
a_1 & a_2 & \cdots & a_n \\
\mid & \mid & & \mid
\end{array}\right]\left[\begin{array}{ccc}
- & b_1^{\top} & - \\
- & b_2^{\top} & - \\
& \vdots & \\
- & b_n^{\top} & -
\end{array}\right]=\sum_{i=1}^n a_i b_i^{\top} .
$$
with the outer product $a_i b_i^{\top}$ defined as: 
$$\mathbf{u} \otimes \mathbf{v}=\mathbf{u v}^{\top}=\left[\begin{array}{l}u_1 \\ u_2 \\ u_3 \\ u_4\end{array}\right]\left[\begin{array}{lll}v_1 & v_2 & v_3\end{array}\right]=\left[\begin{array}{lll}u_1 v_1 & u_1 v_2 & u_1 v_3 \\ u_2 v_1 & u_2 v_2 & u_2 v_3 \\ u_3 v_1 & u_3 v_2 & u_3 v_3 \\ u_4 v_1 & u_4 v_2 & u_4 v_3\end{array}\right]$$

- This is relevant to understand why $\mathbf{AU} =\mathbf{U\Lambda}$ is the correct arrangement for [[Eigenvalue decomposition]]. 
- I think this is also very intuitive: [The key here is to understand that under thing interpretation, we basically scale the columns of A by the value in B]
- lets take $\left[\begin{array}{ll}2 & 4 \\ 3 & 1\end{array}\right]\left[\begin{array}{ll}\lambda_1 & 0 \\ 0 & \lambda_2\end{array}\right]$ as an example: Phonetically we can see this as $\lambda_{1}$ times the first column and zero times the second column + zero times the first column and $\lambda_{2}$-times the second column. 
## Matrix-Vector

$$ \large\tag{3}
\mathbf{C}=\mathbf{A} \mathbf{B}=\mathbf{A}\left[\begin{array}{cccc}
\mid & \mid & & \mid \\
b_1 & b_2 & \cdots & b_p \\
\mid & \mid & & \mid
\end{array}\right]=\left[\begin{array}{cccc}
\mid & \mid & & \mid \\
\mathbf{A} b_1 & \mathbf{A} b_2 & \cdots & \mathbf{A} b_p \\
\mid & \mid & & \mid
\end{array}\right]
$$

## Vector-Matrix

$$\large\tag{4} 
\mathbf{C}=\mathbf{A B}=\left[\begin{array}{ccc}
- & \boldsymbol{a}_1^{\top} & - \\
- & \boldsymbol{a}_2^{\top} & - \\
& \vdots & \\
- & \boldsymbol{a}_m^{\top} & -
\end{array}\right] \mathbf{B}=\left[\begin{array}{ccc}
- & \boldsymbol{a}_1^{\top} \mathrm{B} & - \\
- & \boldsymbol{a}_2^{\top} \mathrm{B} & - \\
& \vdots & \\
- & \boldsymbol{a}_m^{\top} \mathbf{B} & -
\end{array}\right]
$$

