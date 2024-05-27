---
title: Eigenvalue decomposition
date:
  - 27-05-2024
time: 17:15
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: Process
formula: 
aliases: 
modified: 2024-05-27
---
# Eigenvalue decomposition
## Basics

## Diagonalisation

$$\large\tag{}
\mathbf{A U}=\mathbf{U} \Lambda
$$

$$\large\tag{}
\mathbf{A}=\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{-1}
$$

## Eigenvalues and eigenvectors of symmetric matrices

$$\large\tag{}
\mathbf{A}=\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top}=\left(\begin{array}{cccc}
\mid & \mid & & \mid \\
\boldsymbol{u}_1 & \boldsymbol{u}_2 & \cdots & \boldsymbol{u}_n \\
\mid & \mid & & \mid
\end{array}\right)\left(\begin{array}{llll}
\lambda_1 & & & \\
& \lambda_2 & & \\
& & \ddots & \\
& & & \lambda_n
\end{array}\right)\left(\begin{array}{ccc}
- & \boldsymbol{u}_1^{\top} & - \\
- & \boldsymbol{u}_2^{\top} & - \\
& \vdots & \\
- & \boldsymbol{u}_n^{\top} & -
\end{array}\right)
$$
This breaks down for each 
### Checking for positive definiteness


## Geometry of quadratic forms

## Standardizing and whitening data

## Power method

## Deflation

## Eigenvectors optimize quadratic forms

# References
> [!PDF|yellow] [[murphy2022.pdf#page=283&selection=113,0,120,11&color=yellow|murphy2022, p.253]]
> > When A is real and symmetric, it can be shown that all the eigenvalues are real, and the eigenvectors are orthonormal

> [!PDF|yellow] [[murphy2022.pdf#page=283&selection=367,0,381,1&color=yellow|murphy2022, p.253]]
> > Thus multiplying by any symmetric matrix A can be interpreted as multiplying by a rotation matrix $U^T$, a scaling matrix $Λ$, followed by an inverse rotation $U$.


