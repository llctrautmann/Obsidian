---
title: Matrix Inversion
date:
  - 25-05-2024
time: 08:46
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: Concept
formula: $\mathbf{A}^{-1} \mathbf{A}=\mathbf{I}=\mathbf{A} \mathbf{A}^{-1}$
🍙: いや
modified: 2024-05-25
---
# Matrix Inversion
Determinants are only defined for square matrices. For these matrices a determinant is a function that maps $A$ onto $\mathbb{R}$. The inverse of a Matrix is strictly only defined for [square matrices](Fundamental%20Linear%20Maps).

$$\large\tag{1}
\mathbf{A}^{-1} \mathbf{A}=\mathbf{I}=\mathbf{A} \mathbf{A}^{-1}
$$


## Conditions
- applies only to square matrices
- requires $\\det(A) \neg 0$ otherwise the matrix is singular, and squeezes a dimension. Determinants are therefore a measure of volume, which also explains why invertible matrices need a non-zero determinant. If the determinant is zero the volume is reduced to at least a plane. 

> [!PDF|yellow] [[deisenroth2020.pdf#page=107&selection=150,2,164,1&color=yellow|deisenroth2020, p.101]]
> > It turns out that the determinant det(A) is the signed volume of an n-dimensional parallelepiped formed by columns of the matrix A.
> 
> This also explains why a matrix with a det(M) = 0 is so problematic. These matrices are not staying within the geometric space, but transform, the input onto a lower dimensional space. __Thus, the determinant acts as a function that measures the signed volume formed by column vectors composed in a matrix.__

## Rules for Inverse $A^{-1}$

$$\large\tag{2}
\begin{aligned}
\left(\mathbf{A}^{-1}\right)^{-1} & =\mathbf{A} \\
(\mathbf{A B})^{-1} & =\mathbf{B}^{-1} \mathbf{A}^{-1} \\
\left(\mathbf{A}^{-1}\right)^{\top} & =\left(\mathbf{A}^{\top}\right)^{-1} \triangleq \mathbf{A}^{-T}
\end{aligned}
$$

