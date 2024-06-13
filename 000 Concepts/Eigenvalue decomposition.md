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
  - EVD
modified: 2024-06-13
---
# Eigenvalue decomposition
## Basics
- EVD is a technique to decompose **square** matrices
- The principle formula is $\large\mathbf{A}\mathbf{u} = \lambda \mathbf{u}$ 
	- The principle intuition behind [[Eigenthings|EVD]] is the observation that some vectors point in the same direction as before (but possibly scaled) when transformed by a [[Linear Maps|linear map]]. 
	- Eigenvalues are infinitely scalable by a scalar, so $c\mathbf{u}$ is also an eigenvector. 
		- Hence: $\large\mathbf{A}(c \boldsymbol{u})=c \mathbf{A} \boldsymbol{u}=c \lambda \boldsymbol{u}=\lambda(c \boldsymbol{u})$
- The trace of any symmetric matrix is the sum of its eigenvalues, the area of the determinant is the product of the eigenvalues. 
- A common way to rewrite the principle formula is $\large\operatorname{det}(\lambda \mathbf{I}-\mathbf{A})=0$. This makes intuitive sense because we need to squeeze space for $\mathbf{A}$ to result in just scaling. 
- For diagonal matrices the diagonal entries are the eigenvalues
## Diagonalisation


$$\large\tag{1}
\mathbf{A U}=\mathbf{U} \Lambda
$$


We can then diagonalise the matrix by multiplying with the inverse - which only exists if the eigenvectors are [[Vector Independence|independent]]. 
$$\large\tag{2}
\mathbf{A}=\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{-1}
$$

A matrix that can be written in this form is called diagonalisable. 

## Eigenvalues and eigenvectors of symmetric matrices
- Assuming $\mathbf{A}$ is real and symmetrical
	- The eigenvector matrices are also orthonormal:
		- i.e., $\boldsymbol{u}_i^\top \boldsymbol{u}_j=0$ if $i \neq j$, and $\boldsymbol{u}_i^{\top} \boldsymbol{u}_i=1$, where $\boldsymbol{u}_i$ are the eigenvectors.
		- Note that matrices are [[linear maps]] or functions and hence we read them from right to left. So applying $\mathbf{A}$ is equal to a rotation matrix (this follows from the norm preservation of orthogonal matrices), scaling, and another rotation. 

$$\large\tag{3}
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


### Checking for positive definiteness


## Geometry of quadratic forms

## Standardizing and whitening data

This is a placeholder. [^1]

## Power method

## Deflation

## Eigenvectors optimize quadratic forms

# References
> [!PDF|yellow] [[murphy2022.pdf#page=283&selection=113,0,120,11&color=yellow|murphy2022, p.253]]
> > When A is real and symmetric, it can be shown that all the eigenvalues are real, and the eigenvectors are orthonormal

> [!PDF|yellow] [[murphy2022.pdf#page=283&selection=367,0,381,1&color=yellow|murphy2022, p.253]]
> > Thus multiplying by any symmetric matrix A can be interpreted as multiplying by a rotation matrix $U^T$, a scaling matrix $Λ$, followed by an inverse rotation $U$.
# Footnotes

[^1]: [[murphy2022.pdf#page=284&selection=259,0,278,8&color=yellow|murphy2022, p.254]] 