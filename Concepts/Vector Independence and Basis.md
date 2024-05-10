---
title: Vector Independence and Basis
date:
  - 10-05-2024
time: 11:57
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 0
status: Incomplete
modified: 2024-05-10
---
# Vector Independence and Basis
[[Vector Spaces]] define the space-time continuum in which all other operations in machine learning occur. Individual vectors are capable of mapping the vector space either completely or only partially. The [[Null Space]] for example contains all the vectors within a vector space that are a solutions to $\mathbf{A}\mathbf{x} = \mathbf{0}$. 

## Linear Independence 
A set of vectors $\mathbf{v}_1, \ldots, \mathbf{v}_n \in V$ is said to be linearly independent if
$$
\alpha_1 \mathbf{v}_1+\cdots+\alpha_n \mathbf{v}_n=\mathbf{0} \quad \text { implies } \quad \alpha_1=\cdots=\alpha_n=0
$$

`The basic idea is that linearly independent vectors can only have the trivial solution with all coefficients being 0.`

*Example*:
The vector $x_{1}= \left[ 1,2,0\right]^\top$ and $x_{2}= \left[ 2,4,0\right]^\top$ are not linearly independent and hence I can write $2x_{1}-1x_{2}=\mathbf{0}$. But $[0,1]^\top$ and $[1,0]^\top$ are linearly independent and hence the only solution possible is the trivial solution $0x_{1}-0x_{2}=\mathbf{0}$. 

Intuitively, a set of linearly independent vectors consists of vectors that have no redundancy, i.e., if we remove any of those vectors from the set, we will lose something.

### References
> [!PDF|yellow]- [[deisenroth2020.pdf#page=46&selection=212,0,307,1&color=yellow|deisenroth2020, p.40]]
> > Definition 2.12 (Linear (In)dependence). Let us consider a vector space $V$ with $k \in \mathbb{N}$ and $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k \in V$. If there is a non-trivial linear combination, such that $\mathbf{0}=\sum_{i=1}^k \lambda_i \boldsymbol{x}_i$ with at least one $\lambda_i \neq 0$, the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ are linearly dependent. If only the trivial solution exists, i.e., $\lambda_1=\ldots=\lambda_k=0$ the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ are linearly independent.

> [!PDF|yellow]- [[Thomas2018.pdf#page=6&selection=241,2,295,0&color=yellow|Thomas2018, p.6]]
> > set of vectors $v_{1}, ... , v_{n} \in V$ is said to be linearly independent if 
> $$
\alpha_1 \mathbf{v}_1+\cdots+\alpha_n \mathbf{v}_n=\mathbf{0} \quad \text { implies } \quad \alpha_1=\cdots=\alpha_n=0
$$

## Span

$$
\operatorname{span}\left\{\mathbf{v}_1, \ldots, \mathbf{v}_n\right\}=\left\{\mathbf{v} \in V: \exists \alpha_1, \ldots, \alpha_n \text { such that } \alpha_1 \mathbf{v}_1+\cdots+\alpha_n \mathbf{v}_n=\mathbf{v}\right\}
$$

The span of a vector space is the space that every linear combination of the vectors create. For example the vector $[1,0]^\top$ and $[0,1]^\top$ span all vectors in $\mathbb{R}^2$. 

## Basis
If the set of vectors are linearly independent and span then entire [[Vector Spaces]] $V$, they are a basis of the vector space. 

If a vector space is spanned by a finite number of vectors, it is said to be finite-dimensional. Otherwise it is infinite-dimensional. The number of vectors in a basis for a finite-dimensional vector space V is called the dimension of V and denoted dim V .

So for 2D space the dimension is 


> [!PDF|yellow]- [[Thomas2018.pdf#page=6&selection=379,12,379,80&color=yellow|Thomas2018, p.6]]
> > every linearly independent set of vectors forms a basis for its span.


> [!PDF|yellow]- [[Thomas2018.pdf#page=6&selection=380,0,406,1&color=yellow|Thomas2018, p.6]]
> > If a vector space is spanned by a finite number of vectors, it is said to be finite-dimensional. Otherwise it is infinite-dimensional. The number of vectors in a basis for a finite-dimensional vector space V is called the dimension of V and denoted dim V .
> 
> 