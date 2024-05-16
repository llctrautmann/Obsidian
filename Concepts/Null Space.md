---
title: Null Space
date:
  - 16-05-2024
time: 10:06
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 
status: Incomplete
type: Concept
modified: 2024-05-16
---
# Null Space
Some important [[Subspaces]] are induced by linear maps. I assume $T: V \rightarrow W$ is a linear map here. Then, the null space is the subspace this contains all vectors that fall into $\mathbf{0}$ in the new vector space. More elegantly in mathematical notation:


$$\large\tag{1}
\operatorname{null}(T)=\{\mathbf{v} \in V \mid T \mathbf{v}=\mathbf{0}\}
$$
`The null space is all vectors in V that satisify the condition that the linear map V times the vector result in the zero vector.`


the range of the linear map $T$ are all the vectors that I can reach with the linear map $T$. 


$$\large\tag{2}
\operatorname{range}(T)=\{\mathbf{w} \in W \mid \exists \mathbf{v} \in V \text { such that } T \mathbf{v}=\mathbf{w}\}
$$

`The range of T are those vectors w in the vector space W, for which exists a vector in V so that the equation Tv = w has a solution.`

