---
title: Analytic Geometry
date:
  - 15-02-2024
time: 07:30
author: Luca Trautmann
tags: 
series: M4ML
chapter: 2
status: Incomplete
modified: 2024-03-22
---
# Analytic Geometry
## Norms
A norm is a mapping from a vector space $V$ onto $\mathbb{R}^1$. 

> [!Define]
> Definition 3.1 (Norm). A norm on a vector space $V$ is a function
> $$
> \begin{aligned}
> \|\cdot\|: V & \rightarrow \mathbb{R}, \\
> x & \mapsto\|x\|,
> \end{aligned}
> $$
> which assigns each vector $x$ its length $\|x\| \in \mathbb{R}$, such that for all $\lambda \in \mathbb{R}$ and $x, y \in V$ the following hold:
> - Absolutely homogeneous: $\|\lambda x\|=|\lambda|\|x\|$
> - Triangle inequality: $\|\boldsymbol{x}+\boldsymbol{y}\| \leqslant\|\boldsymbol{x}\|+\|\boldsymbol{y}\|$
> - Positive definite: $\|x\| \geqslant 0$ and $\|x\|=0 \Longleftrightarrow x=0$
> 
> In geometric terms, the triangle inequality states that for any triangle, the sum of the lengths of any two sides must be greater than or equal to the length of the remaining side; (Deisenroth et al., 2020, p. 71)

### Common Norms
1. Manhatten Norm: $$
\|x\|_1:=\sum_{i=1}^n\left|x_i\right|
$$
2. Euclidean Norm: 
$$
\|\boldsymbol{x}\|_2:=\sqrt{\sum_{i=1}^n x_i^2}=\sqrt{\boldsymbol{x}^{\top} \boldsymbol{x}}
$$

## Inner Products
__Inner products allow for the introduction of intuitive geometrical concepts, such as the length of a vector and the angle or distance between two vectors.__ A major purpose of inner products is to determine whether vectors are orthogonal to each other.

### Dot Product
$$
\boldsymbol{x}^{\top} \boldsymbol{y}=\sum_{i=1}^n x_i y_i
$$
### General Inner Products
We know from [[Linear Algebra#Linear Mappings]] that we can arrange a linear mapping with respect to addition and multiplication with a scalar as: 

$$\begin{aligned}
\Phi(\boldsymbol{x}+\boldsymbol{y}) & =\Phi(\boldsymbol{x})+\Phi(\boldsymbol{y}) \\
\Phi(\lambda \boldsymbol{x}) & =\lambda \Phi(\boldsymbol{x})
\end{aligned}$$
`Note: 1 = Distributive property , 2 = associative property` 

a bilinear mapping has two arguments and both are linear. Hence:

$$
\begin{aligned}
& \Omega(\lambda x+\psi \boldsymbol{y}, \boldsymbol{z})=\lambda \Omega(\boldsymbol{x}, \boldsymbol{z})+\psi \Omega(\boldsymbol{y}, \boldsymbol{z}) \\
& \Omega(\boldsymbol{x}, \lambda \boldsymbol{y}+\psi \boldsymbol{z})=\lambda \Omega(\boldsymbol{x}, \boldsymbol{y})+\psi \Omega(\boldsymbol{x}, \boldsymbol{z}) .
\end{aligned}
$$


> [!Define 3.2]+
> Let $V$ be a vector space and $\Omega: V \times V \rightarrow \mathbb{R}$ be a bilinear mapping that takes two vectors and maps them onto a real number. Then
> - $\Omega$ is called symmetric if $\Omega(\boldsymbol{x}, \boldsymbol{y})=\Omega(\boldsymbol{y}, \boldsymbol{x})$ for all $x, \boldsymbol{y} \in V$, i.e., the order of the arguments does not matter.
> - $\Omega$ is called positive definite if
> $$
> \forall \boldsymbol{x} \in V \backslash\{\mathbf{0}\}: \Omega(\boldsymbol{x}, \boldsymbol{x})>0, \quad \Omega(\mathbf{0}, \mathbf{0})=0
> $$

> [!Define 3.3]+
> Let $V$ be a vector space and $\Omega: V \times V \rightarrow \mathbb{R}$ be a bilinear mapping that takes two vectors and maps them onto a real number. Then
> - A positive definite, symmetric bilinear mapping $\Omega: V \times V \rightarrow \mathbb{R}$ is called an inner product on $V$. We typically write $\langle\boldsymbol{x}, \boldsymbol{y}\rangle$ instead of $\Omega(\boldsymbol{x}, \boldsymbol{y})$.
> - The pair $(V,\langle\cdot, \cdot\rangle)$ is called an inner product space or (real) vector space with inner product. If we use the dot product defined in (3.5), we call $(V,\langle\cdot, \cdot\rangle)$ a Euclidean vector space.

### Symmetric, Postive Definite Matrices
Due to the bilinearity of the inner product, it holds for all $x,y \in V$ that:
$$
\langle\boldsymbol{x}, \boldsymbol{y}\rangle=\left\langle\sum_{i=1}^n \psi_i \boldsymbol{b}_i, \sum_{j=1}^n \lambda_j \boldsymbol{b}_j\right\rangle=\sum_{i=1}^n \sum_{j=1}^n \psi_i\left\langle\boldsymbol{b}_i, \boldsymbol{b}_j\right\rangle \lambda_j=\hat{\boldsymbol{x}}^{\top} \boldsymbol{A} \hat{\boldsymbol{y}}
$$
That shows that the inner product is uniquely determined through the vectors in A. Furthermore, the positive definiteness of the inner product implies that
$$
\forall x \in V \backslash\{0\}: \boldsymbol{x}^{\top} \boldsymbol{A} \boldsymbol{x}>0 .
$$
If $A \in \mathbb{R}^{n \times n}$ is symmetric and positive defined, then:
$$
\langle\boldsymbol{x}, \boldsymbol{y}\rangle=\hat{\boldsymbol{x}}^{\top} \boldsymbol{A} \hat{\boldsymbol{y}}
$$
defines an inner product with respect to an ordered basis $B$, where $\hat{x}$ and $\hat{y}$ are the coordinate representations of $x, y \in V$ with respect to $B$.
`Note: You can create an new norm with any matrix that fulfuills the requirements set above.`

The following properties hold if $A \in \mathbb{R}^{n \times n}$ is symmetric and positive definite:
- The null space (kernel) of $\boldsymbol{A}$ consists only of 0 because $\boldsymbol{x}^{\top} \boldsymbol{A} \boldsymbol{x}>0$ for all $\boldsymbol{x} \neq \mathbf{0}$. This implies that $\boldsymbol{A x} \neq \mathbf{0}$ if $\boldsymbol{x} \neq \mathbf{0}$.
- The diagonal elements $a_{i i}$ of $\boldsymbol{A}$ are positive because $a_{i i}=\boldsymbol{e}_i^{\top} \boldsymbol{A} \boldsymbol{e}_i>0$, where $\boldsymbol{e}_i$ is the $i^{th}$ vector of the standard basis in $\mathbb{R}^n$.

## Length and Distances
Inner products and norms are closely related in the sense that any inner product induces a norm. 
$$
\|x\|:=\sqrt{\langle x, x\rangle}
$$
`Note: not every norm is induced by an inner product. For example the Manhattan Norm has no corresponding inner product.`

$$ (V,\langle\cdot, \cdot\rangle) $$
Defines a vector space with it's fundamental properties [[Linear Algebra#Vector Spaces]] (closure of inner and outer operation + additions) and also a inner product that adheres to the rules of an inner product.
1. symmetry `basically commutative properities`
2. positive definite `the inner product is always larger 0 except for 0 in which case it is 0`
`Not all vectors spaces also have a defined inner product`

### Cauchy-Schwarz Inequality
If you have a inner product vector space: $(V,\langle\cdot, \cdot\rangle)$. Then any induced norm also satisfies the Cauchy-Schwarz Inequality. 
$$
|\langle\boldsymbol{x}, \boldsymbol{y}\rangle| \leqslant\|\boldsymbol{x}\|\|\boldsymbol{y}\| .
$$
`Note: the absolute value of the inner product of vectors x and y is less than or equal to the product of their magnitudes (or norms)`
### Distance and Metric
> [!Definition 3.6 (Distance and Metric)]
> Consider an inner product space $(V,\langle\cdot, \cdot\rangle)$. Then
> $$
> d(x, y):=\|x-y\|=\sqrt{\langle x-y, x-y\rangle}
> $$
> This is called the distance between the vectors $x$ and $y$.

`Note if the inner product is the dot product` $\boldsymbol{x}^{\top} \boldsymbol{y}=\sum_{i=1}^n x_i y_i$ `then the distance is called the eucledian distance`

The mapping
$$
\begin{aligned}
d: V \times V & \rightarrow \mathbb{R} \\
(\boldsymbol{x}, \boldsymbol{y}) & \mapsto d(\boldsymbol{x}, \boldsymbol{y})
\end{aligned}
$$

is called a **metric**.

> Similar to the length of a vector, the distance between vectors does not require an inner product: a norm is sufficient. If we have a norm induced by an inner product, the distance may vary depending on the choice of the inner product. (Deisenroth et al., 2020, p. 76)

### Properties of Metrics
A metric $d$ satisfies the following:
1. $d$ is positive definite, i.e., $d(\boldsymbol{x}, \boldsymbol{y}) \geqslant 0$ for all $x, \boldsymbol{y} \in V$ and $d(\boldsymbol{x}, \boldsymbol{y})=$ $0 \Longleftrightarrow x=y$.
2. $d$ is symmetric, i.e., $d(\boldsymbol{x}, \boldsymbol{y})=d(\boldsymbol{y}, \boldsymbol{x})$ for all $\boldsymbol{x}, \boldsymbol{y} \in V$.
3. Triangle inequality: $d(\boldsymbol{x}, \boldsymbol{z}) \leqslant d(\boldsymbol{x}, \boldsymbol{y})+d(\boldsymbol{y}, \boldsymbol{z})$ for all $\boldsymbol{x}, \boldsymbol{y}, \boldsymbol{z} \in V$.

`Note: we observe that ⟨x, y⟩ and d(x, y) behave in opposite directions.`
## Angles and Orthogonality
In addition to enabling the definition of lengths of vectors, as well as the distance between two vectors, inner products also capture the geometry of a vector space by defining the angle $\omega$ between two vectors.

$$
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\|\boldsymbol{x}\|\|\boldsymbol{y}\|}
$$
Depending on the inner product used. The angle may vary.

### Orthogonality 
Two vectors are orthogonal iif. $\langle\boldsymbol{x}, \boldsymbol{y}\rangle$ is 0.

$$
x\perp y \Longleftrightarrow \langle\boldsymbol{x}, \boldsymbol{y}\rangle = 0
$$

### Orthonormality
If two vectors are orthogonal and they have both a length of 1 ($||\boldsymbol{x}\|=\|\boldsymbol{y}\| = 1$) the vectors are called orthonormal. 

There are two major conditions that coincide with orthogonal matrices:
1) no changes in length
$$
\|\boldsymbol{A} \boldsymbol{x}\|^2=(\boldsymbol{A} \boldsymbol{x})^{\top}(\boldsymbol{A} \boldsymbol{x})=\boldsymbol{x}^{\top} \boldsymbol{A}^{\top} \boldsymbol{A} \boldsymbol{x}=\boldsymbol{x}^{\top} \boldsymbol{I} \boldsymbol{x}=\boldsymbol{x}^{\top} \boldsymbol{x}=\|\boldsymbol{x}\|^2
$$
3) no changes in angle
$$
\cos \omega=\frac{(\boldsymbol{A} \boldsymbol{x})^{\top}(\boldsymbol{A} \boldsymbol{y})}{\|\boldsymbol{A} \boldsymbol{x}\|\|\boldsymbol{A} \boldsymbol{y}\|}=\frac{\boldsymbol{x}^{\top} \boldsymbol{A}^{\top} \boldsymbol{A} y}{\sqrt{\boldsymbol{x}^{\top} \boldsymbol{A}^{\top} \boldsymbol{A} x \boldsymbol{y}^{\top} \boldsymbol{A}^{\top} \boldsymbol{A} y}}=\frac{\boldsymbol{x}^{\top} \boldsymbol{y}}{\|\boldsymbol{x}\|\|\boldsymbol{y}\|},
$$
This holds because orthogonal matrices have the following property:
$$
\boldsymbol{A} \boldsymbol{A}^{\top}=\boldsymbol{I}=\boldsymbol{A}^{\top} \boldsymbol{A},
$$
which implies that
$$
\boldsymbol{A}^{-1}=\boldsymbol{A}^{\top}
$$

## Orthonormal Basis

> [!Definition 3.9 (Orthonormal Basis)]-
> Consider an $n$-dimensional vector space $V$ and a basis $\left\{\boldsymbol{b}_1, \ldots, \boldsymbol{b}_n\right\}$ of $V$. If
> $$
> \begin{aligned}
> & \left\langle\boldsymbol{b}_i, \boldsymbol{b}_j\right\rangle=0 \quad \text { for } i \neq j \\
> & \left\langle\boldsymbol{b}_i, \boldsymbol{b}_i\right\rangle=1
> \end{aligned}
> $$
> for all $i, j=1, \ldots, n$ then the basis is called an orthonormal basis (ONB). If only (3.33) is satisfied, then the basis is called an orthogonal basis. Note that (3.34) implies that every basis vector has length/norm 1.

We can use Gaussian elimination to find a basis for a vector space spanned by a set of vectors. Assume we are given a set $\left\{\tilde{b}_1, \ldots, \tilde{b}_n\right\}$ of non-orthogonal and unnormalized basis vectors. We concatenate them into a matrix $\tilde{B}=\left[\tilde{b}_1, \ldots, \tilde{b}_i\right]$ and apply Gaussian elimination to the augmented matrix (Section 2.3.2) $\left[\tilde{B} \tilde{B}^{\top}|\tilde{B}|\right.$ to obtain an orthonormal basis. This constructive way to iteratively build an orthonormal basis $\left\{b_1, \ldots, b_n\right\}$ is called the [Gram-Schmidt process]


## Orthogonal Complement
Vector spaces can also be orthogonal to each other. 

Consider, $V$ and $U \subseteq V$, with dimension $D$ and $M$. Then its orthogonal complement $U^{\perp}$ is a $(D-M)$ dimensional subspace of $V$ and contains all  vectors in $V$ that are orthogonal to every vector in $U$. Furthermore $$
U \cap U^{\perp}=\{0\}
$$
so that any vector $x \in V$ can be decomposed into
$$
\boldsymbol{x}=\sum_{m=1}^M \lambda_m \boldsymbol{b}_m+\sum_{j=1}^{\bar{D}-M} \psi_j \boldsymbol{b}_j^1, \quad \lambda_m, \psi_j \in \mathbb{R},
$$
$$
\text { where }\left(b_1, \ldots, b_M\right) \text { is a basis of } U \text { and }\left(b_1^{\perp} \ldots, b_{D-M}^{\perp}\right) \text { is a basis of } U^{\perp} \text {. }
$$
`note: in 3D we can hence find a 2D plane orthogonal to any other plane in 3D. With any orthogonal vector to a plane in 3D forming a basis for the orthogonal vector space.`

## Inner Product of Functions
The concept of an inner product can be generalized to vectors with an infinite number of entries (countably infinite) and also continuous-valued functions (uncountably infinite). Then the sum over individual components of vectors turns into an integral.

An inner product of two functions $u: \mathbb{R} \rightarrow \mathbb{R}$ and $v: \mathbb{R} \rightarrow \mathbb{R}$ can be defined as the definite integral
$$
\langle u, v\rangle:=\int_a^b u(x) v(x) d x
$$
If the integral solves to 0, the functions are orthogonal to each other. 
`Note: sin and cos are examples in the interval [-pi, pi] or [0,2pi]`

## Orthogonal Projections
tbc. 

## Rotations
A rotation is a linear mapping (more specifically, an automorphism of rotation a Euclidean vector space) that rotates a plane by an angle θ about the origin, i.e., the origin is a fixed point. 

Rotations $\Phi$ are linear mappings so that we can express them by a rotation matrix $R(\theta)$. Trigonometry (see Figure 3.16) allows us to determine the coordinates of the rotated axes (the image of $\Phi$ ) with respect to the standard basis in $\mathbb{R}^2$. We obtain
$$
\Phi\left(\boldsymbol{e}_1\right)=\left[\begin{array}{c}
\cos \theta \\
\sin \theta
\end{array}\right], \quad \Phi\left(e_2\right)=\left[\begin{array}{c}
-\sin \theta \\
\cos \theta
\end{array}\right] .
$$

Therefore, the rotation matrix that performs the basis change into the rotated coordinates $\boldsymbol{R}(\theta)$ is given as
$$
\boldsymbol{R}(\theta)=\left[\begin{array}{ll}
\Phi\left(e_1\right) & \Phi\left(e_2\right)
\end{array}\right]=\left[\begin{array}{cc}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{array}\right] .
$$

### Rotations in $n$-Dimensions
tbc. 
### Properties of Rotations
- Rotations preserve distances, i.e., $\|x-y\|=\left\|\boldsymbol{R}_\theta(\boldsymbol{x})-\boldsymbol{R}_\theta(\boldsymbol{y})\right\|$. 
- Rotations preserve angles, i.e., the angle between $\boldsymbol{R}_\theta \boldsymbol{x}$ and $\boldsymbol{R}_\theta \boldsymbol{y}$ equals the angle between $x$ and $\boldsymbol{y}$.
- Rotations in three+ dimensions are generally not commutative. 

`Note: the order in which rotations are applied is important, even if they rotate about the same point. Except in 2D. `











