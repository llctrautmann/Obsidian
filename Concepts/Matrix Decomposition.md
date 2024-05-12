---
title: Matrix Decomposition
date:
  - 05-03-2024
time: 17:04
author: Luca Trautmann
tags: 
series: M4ML
chapter: 3
status: Incomplete
modified: 2024-03-26
---
# Matrix Decomposition

![[Matrix_Decomp.png]]
## Determinant and Trace
Determinants are only defined for square matrices. For these matrices a determinant is a function that maps $A$ onto $\mathbb{R}$. 
$$
\operatorname{det}(\boldsymbol{A})=\left|\begin{array}{cccc}
a_{11} & a_{12} & \ldots & a_{1 n} \\
a_{21} & a_{22} & \ldots & a_{2 n} \\
\vdots & & \ddots & \vdots \\
a_{n 1} & a_{n 2} & \ldots & a_{n n}
\end{array}\right|
$$
If the matrix determinant is non-zero the matrix is invertible. 


Determinants are also a measure of volume, which also explains why invertible matrices need a non-zero determinant. 

> It turns out that the determinant det(A) is the signed volume of an n-dimensional parallelepiped formed by columns of the matrix A. (Deisenroth et al., 2020, p. 101). This also explains why a matrix with a det(M) = 0 is so problematic. These matrices are not staying within the geometric space, but transform, the input onto a lower dimensional space. __Thus, the determinant acts as a function that measures the signed volume formed by column vectors composed in a matrix.__

There are closed form expressions for the determinant for small matrices (see [here](https://www.google.com/google_determinant_dumbass))

### Triangular and diagonal Matrices
We call a square matrix $\boldsymbol{T}$ an upper-triangular matrix if $T_{i j}=0$ for $i>j$, i.e., the matrix is zero below its diagonal. Analogously, we define a lower-triangular matrix as a matrix with zeros above its diagonal. For a triangular matrix $\boldsymbol{T} \in \mathbb{R}^{n \times n}$, the determinant is the product of the diagonal elements, i.e.,
$$
\operatorname{det}(\boldsymbol{T})=\prod_{i=1}^n T_{i i}
$$

`Note: maybe this could be interesting in the superresolution pipeline.`

### Laplacian Expansion
> [!Define]
> Theorem 4.2 (Laplace Expansion). Consider a matrix $A \in \mathbb{R}^{n \times n}$. Then, for all $j=1, \ldots, n$ :
> 1. Expansion along column $j$
> $$
> \operatorname{det}(\boldsymbol{A})=\sum_{k=1}^n(-1)^{k+j} a_{k j} \operatorname{det}\left(\boldsymbol{A}_{k, j}\right) .
> $$
> 2. Expansion along row $j$
> $$
> \operatorname{det}(\boldsymbol{A})=\sum_{k=1}^n(-1)^{k+j} a_{j k} \operatorname{det}\left(\boldsymbol{A}_{j, k}\right) .
> $$
> 
> Here $\boldsymbol{A}_{k, j} \in \mathbb{R}^{(n-1) \times(n-1)}$ is the submatrix of $\boldsymbol{A}$ that we obtain when deleting row $k$ and column $j$.

### Sarrus Rule
## Eigenvalue and Eigenvector
Every linear mapping ([[Concepts/Linear Algebra#Linear Mappings]]) `AKA: Matrices that adhere to the associatve and distributive property` has a unique transformation matrix give the underlying ordered basis. 

Geometrically, the eigenvector corresponding to a nonzero eigenvalue points in a direction that is stretched by the linear mapping. The eigenvalue is the factor by which it is stretched. If the eigenvalue is negative, the direction of the stretching is flipped.


> [!Example]-
> ### Original Space (A) and Target Space (B)
> 
> Imagine we have two vector spaces, A and B, both represented in 2D. We want to transform vectors from space A to space B.
> 
> ### Ordered Basis
> 
> For both spaces, we need an ordered basis to define how vectors are represented.
> 
> - For space A, let's choose the standard basis vectors \(e_1 = (1, 0)\) and \(e_2 = (0, 1)\). This is a common choice and makes our initial space the standard Cartesian coordinate system.
> - For space B, let's choose a different basis, say \(b_1 = (2, 0)\) and \(b_2 = (0, 2)\). This basis still spans the 2D space but scales the standard basis by a factor of 2.
> 
> ### Transformation Matrix
> 
> We want a transformation matrix that maps vectors from space A to space B. Given our choice of basis vectors, this transformation will effectively scale any vector in space A by a factor of 2 to get the corresponding vector in space B.
> 
> The transformation matrix \(T\) that does this, using the standard basis for A and our chosen basis for B, is:
> 
> $$T = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}$$
> 
> ### Example Transformation
> 
> Let's transform a vector \(v = (1, 1)\) from space A to space B.
> 
> 1. In space A, \(v\) is simply \(1 \cdot e_1 + 1 \cdot e_2\).
> 2. To transform \(v\) to space B, we multiply it by our transformation matrix \(T\):
> 
> $$Tv = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 2 \end{pmatrix}$$
> 
> So, the vector \(v = (1, 1)\) in space A is mapped to the vector \(v' = (2, 2)\) in space B by the transformation matrix \(T\), which was derived based on the ordered bases chosen for each space. This example illustrates how the transformation matrix—and thus the mapping from A to B—depends on the underlying ordered basis of both spaces.

The eigenvalues of a linear mapping `matrix` $A$ shows how the eigenvectors are transformed by the linear mapping.


> [!Definition 4.6.]
>  Let $A \in \mathbb{R}^{n \times n}$ be a square matrix. Then $\lambda \in \mathbb{R}$ is an eigenvalue of $\boldsymbol{A}$ and $\boldsymbol{x} \in \mathbb{R}^n \backslash\{\mathbf{0}\}$ is the corresponding eigenvector of $\boldsymbol{A}$ if
> $$
> \boldsymbol{A x}=\lambda \boldsymbol{x} .
> $$
> 
> We call this the eigenvalue equation.
> The following conditions hold:
> - $\lambda$ is an eigenvalue of $\boldsymbol{A} \in \mathbb{R}^{n \times n}$.
> - There exists an $\boldsymbol{x} \in \mathbb{R}^n \backslash\{\boldsymbol{0}\}$ with $\boldsymbol{A x}=\lambda \boldsymbol{x}$, or equivalently, $(\boldsymbol{A}-$ $\left.\lambda \boldsymbol{I}_n\right) \boldsymbol{x}=\mathbf{0}$ can be solved non-trivially, i.e., $\boldsymbol{x} \neq \mathbf{0}$.
> - $\operatorname{rk}\left(\boldsymbol{A}-\lambda \boldsymbol{I}_n\right)<n$.
> - $\operatorname{det}\left(\boldsymbol{A}-\lambda \boldsymbol{I}_n\right)=0$

`Note: The eigenvalues and eigenvectors are non-unique and can be scaled. All videos that are collinear to x are also eigenvectors of A.`

### Eigenspace and Eigenspectrum


## Cholesky Decomposition 

## Eigendecomposition and Diagonalisation

## SVD

## Matrix Approximation

## Matrix Phylogeny
