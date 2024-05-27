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
There are four ways of looking at matrix-matrix multiplication and depending on the situation it is useful to look at a problem form either perspective. 

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

- This is relevant to understand why $\mathbf{AU} =\mathbf{U\Lambda}$ is the correct arrangement for [[Eigenvalue decomposition]]. 
- I think this is also very intuitive: [The key here is to understand that under thing interpretation, we basically scale the columns of A by the value in B]
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

