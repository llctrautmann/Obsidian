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

## Linear Indenpendence 
A set of vectors $\mathbf{v}_1, \ldots, \mathbf{v}_n \in V$ is said to be linearly independent if
$$
\alpha_1 \mathbf{v}_1+\cdots+\alpha_n \mathbf{v}_n=\mathbf{0} \quad \text { implies } \quad \alpha_1=\cdots=\alpha_n=0
$$

`This requires some unpacking:`
`The basic idea is`
## Span

$$
\operatorname{span}\left\{\mathbf{v}_1, \ldots, \mathbf{v}_n\right\}=\left\{\mathbf{v} \in V: \exists \alpha_1, \ldots, \alpha_n \text { such that } \alpha_1 \mathbf{v}_1+\cdots+\alpha_n \mathbf{v}_n=\mathbf{v}\right\}
$$

The span of a vector space is the space that every linear combination of the vectors create. For example the vector $[1,0]^\top$ and $[0,1]^\top$ span all vectors in $\mathbb{R}^2$. 

## Basis

> [!Define]+
> Definition 2.12 (Linear (In)dependence). Let us consider a vector space $V$ with $k \in \mathbb{N}$ and $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k \in V$. If there is a non-trivial linear combination, such that $\mathbf{0}=\sum_{i=1}^k \lambda_i \boldsymbol{x}_i$ with at least one $\lambda_i \neq 0$, the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ are linearly dependent. If only the trivial solution exists, i.e., $\lambda_1=\ldots=\lambda_k=0$ the vectors $\boldsymbol{x}_1, \ldots, \boldsymbol{x}_k$ are linearly independent.

From the definition above we can see that, if the vectors are linearly independent they form a basis



> Linear independence is one of the most important concepts in linear algebra. Intuitively, a set of linearly independent vectors consists of vectors that have no redundancy, i.e., if we remove any of those vectors from the set, we will lose something. *from [[Linear Algebra]]*

