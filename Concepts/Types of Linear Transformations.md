---
title: Types of Linear Transformations
date:
  - 01-04-2024
time: 16:31
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 2
status: Incomplete
modified: 2024-04-02
link: https://gregorygundersen.com/blog/2018/10/24/matrices/
---
# Types of Linear Transformations

![[linear_transformations.png]]

One key aspect of linear transformations that I need to keep in mind about linear transformations is that they are polynomials of degree one or less. `Research`

## Specific Types of Matrix Transformations
### Diagonal Matrices

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

### Shear Matrices

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

### Orthogonal Matrices
Orthogonal vectors have a dot product of 0. So in an orthogonal matrix all columns and rows are orthogonal unit vectors (technically this should end up as a orthonormal [[Analytic Geometry#Orthogonality]]). 

Orthogonal matrices can flip or rotate a vector space, but I cannot stretch or compress it.

Other useful properties:
1) preserves angles
2) preserves lengths
3) preserves area








