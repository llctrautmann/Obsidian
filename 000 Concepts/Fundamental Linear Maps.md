---
title: Fundamental Linear Maps
date:
  - 01-04-2024
time: 16:31
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 2
type: Concept
link: https://gregorygundersen.com/blog/2018/10/24/matrices/
modified: 2024-06-12
aliases:
  - diagonal matrices
---
# Fundamental Linear Maps
## Square Matrices
Same input dimension and output dimension. 


$$\large
\mathbf{A}=\left(\begin{array}{ll}
a & b \\
c & d
\end{array}\right)
$$


Square matrices are the only matrices that are strictly invertible. Requires [[Determinant]] to be non-zero, thereby we maintain the dimensionality of the space and the columns are independent. The matrix is then called non-singular. 

## Identity Matrix
In $\mathbb{R}^{n \times n}$, we define the identity matrix

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

as the $n \times n$-matrix containing 1 on the diagonal and 0 everywhere else. It does nothing to the basis vectors it is applied to. 


## Diagonal Matrices

$$
\left[\begin{array}{lllll}
\alpha_1 & & & & \\
& \ddots & & & \\
& & \alpha_i & & \\
& & & \ddots & \\
& & & & \alpha_n
\end{array}\right]\left[\begin{array}{c}
x_1 \\
\vdots \\
x_i \\
\vdots \\
x_n
\end{array}\right]
$$

Diagonal matrices are very nice, because they only have a limited range of possible consequences they can have. They can stretch or squeeze or reflect the original basis vectors by the scalars they have on the diagonal of the matrix [^1]. 

## Tiangular Matrix
- either upper triangular or lower triangular
- useful property, that the eigenvalues are on the diagonal and that hence the [[Determinant]] is the product of the diagonal [[Eigenthings|eigenvalues]] [^2]. 


## Positive Definite Matrices
!![[Positive Definite Matrices|positive semi-definite]]


## Shear Matrices

$$
\left[\begin{array}{ccccc}
\alpha_1 & \ldots & \beta & & \\
& \ddots & \vdots & & \\
& & \alpha_i & & \\
& & & \ddots & \\
& & & & \alpha_n
\end{array}\right]\left[\begin{array}{c}
x_1 \\
\vdots \\
x_i \\
\vdots \\
x_n
\end{array}\right]
$$

A shear matrix moves the column with the off diagonal elements and hence shears the space. 

![[shear.png]]


## Orthogonal Matrices
![[Orthogonality#Orthogonal Matrix|orthogonality]]


Orthogonal vectors have a dot product of 0. So in an orthogonal matrix all columns and rows are orthogonal unit vectors (technically this should end up as a orthonormal [[Analytic Geometry#Orthogonality]]). 

Orthogonal matrices can flip or rotate a vector space, but I cannot stretch or compress it.

Other useful properties:
1) preserves angles
2) preserves lengths
3) preserves area

This is an example for a rotation matrix around the z axis
$$\large
\mathbf{R}(\alpha)=\left(\begin{array}{ccc}
\cos (\alpha) & -\sin (\alpha) & 0 \\
\sin (\alpha) & \cos (\alpha) & 0 \\
0 & 0 & 1
\end{array}\right)
$$
## Symmetric Matrices

$$\large\tag{4}
\mathbf{A} = \mathbf{A}^{\top}
$$

Symmetric matrices have strong implications (-> [[Eigenvalue decomposition|EVD]])

## Transpose
The transpose can generally be obtained by switching the rows and columns of a matrix. It is abbreviated with $\boldsymbol{A}^{\top}$. If $\boldsymbol{A}^{\top}= \boldsymbol{A}^{-\top}$ the matrix is __symmetric__. 

$$
\left(\mathbf{A}^{\top}\right)_{i j}=A_{j i}
$$

The general properties of the transpose are: 

$$\large
\begin{aligned}
& \left(\mathbf{A}^{\top}\right)^{\top}=\mathbf{A} \\
& (\mathbf{A}+\mathbf{B})^{\top}=\mathbf{A}^{\top}+\mathbf{B}^{\top} \\
& (\alpha \mathbf{A})^{\top}=\alpha \mathbf{A}^{\top} \\
& (\mathbf{A B})^{\top}=\mathbf{B}^{\top} \mathbf{A}^{\top}
\end{aligned}
$$



# Footnotes

[^1]: [[murphy2022.pdf#page=274&selection=12,0,43,1&color=yellow|murphy2022, p.244]]
[^2]: [[murphy2022.pdf#page=268&selection=22,0,41,1&color=yellow|murphy2022, p.238]]