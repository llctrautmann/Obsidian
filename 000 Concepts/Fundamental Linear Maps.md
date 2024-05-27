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
modified: 2024-05-27
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

Diagonal matrices are very nice, because they only have a limited range of possible consequences they can have. They can stretch or squeeze or reflect the original basis vectors by the scalars they have on the diagonal of the matrix. 

> [!PDF|yellow] [[murphy2022.pdf#page=274&selection=12,0,43,1&color=yellow|murphy2022, p.244]]
> > If we pre-multiply X by a diagonal matrix S = diag (s), where s is an N -vector, then we just scale each row of X by the corresponding scale factor in s:
> 
> In the Murphy book are good examples to see this. Also use a sheer matrix to easily verify behaviour. Depending on the order of the linear map/matrix  I scale the rows or the columns ($AB \neq BA$). 



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



## Orthogonal Matrices
![[Orthogonality#Orthogonal Matrix|orthogonality]]


Orthogonal vectors have a dot product of 0. So in an orthogonal matrix all columns and rows are orthogonal unit vectors (technically this should end up as a orthonormal [[Analytic Geometry#Orthogonality]]). 

Orthogonal matrices can flip or rotate a vector space, but I cannot stretch or compress it.

Other useful properties:
1) preserves angles
2) preserves lengths
3) preserves area

## Symmetric Matrices

$$\large\tag{4}
\mathbf{A} = \mathbf{A}^{\top}
$$

Symmetric matrices have strong implications (-> [[Eigendecomposition]])


## Positive Semi-definite Matrices
- [this is not completed]