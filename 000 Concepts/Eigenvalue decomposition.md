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
modified: 2024-06-14
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
- For diagonal matrices the diagonal entries are the [[Eigenthings|eigenvalues]] [^2].

## Diagonalisation
$\large\mathbf{A}\mathbf{u} = \lambda \mathbf{u}$ needs to be extended to generalise to matrices[^4]. 

$$\large\tag{1}
\mathbf{A U}=\mathbf{U} \Lambda
$$


We can then diagonalise the matrix [^5] by multiplying with the inverse - which only exists if the eigenvectors are [[Vector Independence|independent]]. A matrix that can be written in this form is called diagonalisable [^3]. 

$$\large\tag{2}
\mathbf{A}=\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{-1}
$$



## Eigenvalues and eigenvectors of symmetric matrices
- Assuming $\mathbf{A}$ is real and symmetrical
	- The eigenvector matrices are also orthonormal:
		- i.e., $\boldsymbol{u}_i^\top \boldsymbol{u}_j=0$ if $i \neq j$, and $\boldsymbol{u}_i^{\top} \boldsymbol{u}_i=1$, where $\boldsymbol{u}_i$ are the eigenvectors.
		- Note that matrices are [[linear maps]] or functions and hence we read them from right to left. So applying $\mathbf{A}$ is equal to a rotation matrix (this follows from the norm preservation of orthogonal matrices), scaling, and another rotation. 

$$\large\tag{3}
\begin{aligned}
\mathbf{A} & =\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top}=\left(\begin{array}{cccc}
\mid & \mid & & \mid \\
\boldsymbol{u}_1 & \boldsymbol{u}_2 & \cdots & \boldsymbol{u}_n \\
\mid & \mid & & \mid
\end{array}\right)\left(\begin{array}{cccc}
\lambda_1 & & & \\
& \lambda_2 & & \\
& & \ddots & \\
& & & \lambda_n
\end{array}\right)\left(\begin{array}{ccc}
- & \boldsymbol{u}_1^{\top} & - \\
- & \boldsymbol{u}_2^{\top} & - \\
& \vdots & \\
- & \boldsymbol{u}_n^{\top} & -
\end{array}\right) \\
& =\lambda_1\left(\begin{array}{c}
\mid \\
u_1 \\
\mid
\end{array}\right)\left(\begin{array}{lll}
- & \boldsymbol{u}_1^{\top} & -
\end{array}\right)+\cdots+\lambda_n\left(\begin{array}{c}
\mid \\
u_n \\
\mid
\end{array}\right)\left(\begin{array}{llll}
- & \boldsymbol{u}_n^{\top} & -
\end{array}\right)=\sum_{i=1}^n \lambda_i \mathbf{u}_i \mathbf{u}_i^{\top}
\end{aligned}
$$


- Rotating, unscaling and rotating back [^6]. 



### Checking for positive definiteness
To check for semi-definiteness we check the quadratic form and decompose the matrix into its components.
$$\large\tag{4}
\boldsymbol{x}^{\top} \mathbf{A} \boldsymbol{x}=\boldsymbol{x}^{\top} \mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top} \boldsymbol{x}=\boldsymbol{y}^{\top} \boldsymbol{\Lambda} \boldsymbol{y}=\sum_{i=1}^n \lambda_i y_i^2
$$
- the sign of the resulting scalar is entirely dependent on the sign of the eigenvalues [^7]. 
	- depending on the number of negative or positive eigenvalues the matrix is positive/negative definite, semi-definite, or indefinite
\



## Geometry of quadratic forms
A quadratic form is a function that can be written as

$$\large\tag{5}
f(\boldsymbol{x})=\boldsymbol{x}^{\top} \mathbf{A} \boldsymbol{x}
$$

where $x \in \mathbb{R}^n$ and $\mathbf{A}$ is a positive definite, symmetric $n$-by- $n$ matrix. Let $\mathbf{A}=\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top}$ be a diagonalization of $\mathbf{A}$. Hence we can write

$$\large\tag{6} 
f(x)=x^{\top} \mathbf{A} x=x^{\top} \mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top} \boldsymbol{x}=y^{\top} \boldsymbol{\Lambda} y=\sum_{i=1}^n \lambda_i y_i^2
$$

where $y_i=\boldsymbol{x}^{\top} \boldsymbol{u}_i$ and $\lambda_i>0$ (since $\mathbf{A}$ is positive definite). The level sets of $f(x)$ define hyper-ellipsoids[^8]. For example, in 2d, we have

$$ \large\tag{7}
\lambda_1 y_1^2+\lambda_2 y_2^2=r
$$

which is the equation of a 2d ellipse. The eigenvectors determine the orientation of the ellipse, and the eigenvalues determine how elongated it is. In particular, the major and minor semi-axes of the ellipse satisfy $a^{-2}=\lambda_1$ and $b^{-2}=\lambda_2$. In the case of a Gaussian distribution, we have $\mathbf{A}=\boldsymbol{\Sigma}^{-1}$, **so small values of $\lambda_i$ correspond to directions where the posterior has low precision and hence high variance**.



## Standardizing and whitening data

This is a placeholder. [^1]

# Methodology
## Power method
The power method is a iterative algorithm for computing the eigenvectors corresponding to the largest eigenvalue of a real, symmetric matrix [^9]. 

1. Let $\mathbf{A}$ be a matrix with orthonormal [[Eigenthings|eigenvectors]] $u_i$ and eigenvalues $\left|\lambda_1\right|>\left|\lambda_2\right| \geq \cdots \geq\left|\lambda_m\right| \geq 0$.
	1. Then we know: $\mathbf{A} =\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\top}$ 
2. Let $v_{(0)}$ be a vector in the [[Range|column space]] $\mathbf{A}\mathbf{x}= \mathbf{v_{(0)}}$
3. I can rewrite this as: $\Large \boldsymbol{v}_0=\overbrace{\mathbf{U}\left(\boldsymbol{\Lambda U}^{\top} \boldsymbol{x}\right)}^{A x}=a_1 \boldsymbol{u}_1+\cdots+a_m \boldsymbol{u}_m$ [^10] 
4. We iteratively multiply $v$ by $\mathbf{A}$ and renormalise
	1. $\large v_t \propto A v_{t-1}$ 





## Deflation

## Eigenvectors optimize quadratic forms

# References
> [!PDF|yellow] [[murphy2022.pdf#page=283&selection=113,0,120,11&color=yellow|murphy2022, p.253]]
> > When A is real and symmetric, it can be shown that all the eigenvalues are real, and the eigenvectors are orthonormal

> [!PDF|yellow] [[murphy2022.pdf#page=283&selection=367,0,381,1&color=yellow|murphy2022, p.253]]
> > Thus multiplying by any symmetric matrix A can be interpreted as multiplying by a rotation matrix $U^T$, a scaling matrix $Λ$, followed by an inverse rotation $U$.
# Footnotes

[^1]: [[murphy2022.pdf#page=284&selection=259,0,278,8&color=yellow|murphy2022, p.254]] 
[^2]: [[murphy2022.pdf#page=282&selection=318,0,318,81&color=yellow|murphy2022, p.252]]
[^3]: [[murphy2022.pdf#page=283&selection=84,0,107,1&color=yellow|murphy2022, p.253]] 
[^4]: Note: [[Matrix-Matrix Multiplication#Outer-Products (Scaling)]] for more information on the order of the matrices. 
[^5]: Note: Multiply by the inverse on both sides
[^6]: [[murphy2022.pdf#page=283&selection=436,0,436,64&color=yellow|murphy2022, p.253]] 
[^7]: [[murphy2022.pdf#page=283&selection=490,3,502,3&color=yellow|murphy2022, p.253]] 
[^8]: [[Geometry_Quadratic_Form.png]]
[^9]: [[murphy2022.pdf#page=286&selection=24,0,29,37&color=yellow|murphy2022, p.256]]
[^10]: Note: This is first [[Matrix-Matrix Multiplication#Outer-Products (Scaling)]] and then vector matrix multiplication 