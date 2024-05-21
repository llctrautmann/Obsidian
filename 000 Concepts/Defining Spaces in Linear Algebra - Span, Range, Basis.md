---
title: "Defining Spaces in Linear Algebra: Span, Range, Basis"
date:
  - 17-05-2024
time: 22:23
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: 
type: Concept
modified: 2024-05-17
---
# Defining Spaces in Linear Algebra: Span, Range, Basis
## Span
Consider [[Vector Spaces]]

$$\large\tag{1}
(\mathcal{V},+, \cdot)
$$

and a set of vectors $\mathcal{A}=\{x_{1}, x_{2},\dots, x_{n}\} \subseteq (\mathcal{V},+, \cdot)$. If every vector $\operatorname{v} \in \mathcal{V}$ can be expressed as a linear combination of $\{x_{1}, x_{2},\dots, x_{n}\}$, $\mathcal{A}$ is called a __generating set__ of $\mathcal{V}$. The set of all linear combinations of vectors in $\mathcal{A}$ is called the __span__. 

The notation for a vectors space is
$$
V=\operatorname{span}[\mathcal{A}]
$$
Generating sets are sets of vectors that span vector (sub)spaces, i.e., every vector can be represented as a linear combination of the vectors in the generating set. 



$$
\operatorname{span}\left\{\mathbf{v}_1,\ldots, \mathbf{v}_n\right\}=\left\{\mathbf{v}\in V:\exists \alpha_1, \ldots,\alpha_n\text{ such that }\alpha_1 \mathbf{v}_1+\cdots+\alpha_n\mathbf{v}_n=\mathbf{v}\right\}
$$

The span of a vector space is the space that every linear combination of the vectors create. For example the vector $[1,0]^\top$ and $[0,1]^\top$ span all vectors in $\mathbb{R}^2$. 

## Range
The range of the linear map $T$ are all the vectors that I can reach with the linear map $T$. 


$$\large\tag{2}
\operatorname{range}(T)=\{\mathbf{w} \in W \mid \exists \mathbf{v} \in V \text { such that } T \mathbf{v}=\mathbf{w}\}
$$

`The range of T are those vectors w in the vector space W, for which exists a vector in V so that the equation Tv = w has a solution.`

## Basis

**Basis**: set of vectors with which we can represent every vector in the vector space by adding them together and scaling them. Alternatively, it is correct to say: A basis is a minimal generating set of maximal linearly independent set of vectors.


Think:
$$
\mathbf{e}_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \quad
\mathbf{e}_2 = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}, \quad
\mathbf{e}_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}
$$

You can build any vector in 3D from these vector just with addition as well as scalar multiplication.

## Span

$$
\operatorname{span}\left\{\mathbf{v}_1,\ldots, \mathbf{v}_n\right\}=\left\{\mathbf{v}\in V:\exists \alpha_1, \ldots,\alpha_n\text{ such that }\alpha_1 \mathbf{v}_1+\cdots+\alpha_n\mathbf{v}_n=\mathbf{v}\right\}
$$

The span of a vector space is the space that every linear combination of the vectors create. For example the vector $[1,0]^\top$ and $[0,1]^\top$ span all vectors in $\mathbb{R}^2$. 

## Basis
If the set of vectors are linearly independent and span then entire [[Vector Spaces]] $V$, they are a basis of the vector space. 

If a vector space is spanned by a finite number of vectors, it is said to be finite-dimensional. Otherwise it is infinite-dimensional. The number of vectors in a basis for a finite-dimensional vector space V is called the dimension of V and denoted dim V .

> [!PDF|yellow]- [[Thomas2018.pdf#page=6&selection=379,12,379,80&color=yellow|Thomas2018, p.6]]
> > every linearly independent set of vectors forms a basis for its span.

> [!PDF|yellow]- [[Thomas2018.pdf#page=6&selection=380,0,406,1&color=yellow|Thomas2018, p.6]]
> > If a vector space is spanned by a finite number of vectors, it is said to be finite-dimensional. Otherwise it is infinite-dimensional. The number of vectors in a basis for a finite-dimensional vector space V is called the dimension of V and denoted $dim(V)$.
> 
