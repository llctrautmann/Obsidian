---
title: Representations of Linear Maps
date:
  - 14-05-2024
time: 14:21
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-14
---
# Representations of Linear Maps
[[Linear Maps]] are concretely matrices and abstractly [[Functions]] that connect vector spaces. 

## Coordinates

> [!PDF|yellow] [[deisenroth2020.pdf#page=56&selection=193,0,197,0&color=yellow|deisenroth2020, p.50]]
> > Definition 2.18 (Coordinates). Consider a vector space $V$ and an ordered basis $B=\left(\boldsymbol{b}_1, \ldots, \boldsymbol{b}_n\right)$ of $V$. For any $\boldsymbol{x} \in V$ we obtain a unique representation (linear combination)
> $$
> \boldsymbol{x}=\alpha_1 \boldsymbol{b}_1+\ldots+\alpha_n \boldsymbol{b}_n
> $$
> of $\boldsymbol{x}$ with respect to $B$. Then $\alpha_1, \ldots, \alpha_n$ are the coordinates of $\boldsymbol{x}$ with respect to $B$, and the vector
> $$
> \boldsymbol{\alpha}=\left[\begin{array}{c}
> \alpha_1 \\
> \vdots \\
> \alpha_n
> \end{array}\right] \in \mathbb{R}^n
> $$
> is the coordinate vector/coordinate representation of $\boldsymbol{x}$ with respect to the ordered basis $B$.

> 
## A matrix is a linear map is a function. 
Every matrix induces a linear map $T:\mathbb{R}^n \rightarrow \mathbb{R}^m$. 

`this is what I mean with` [[Moving between Dimensions]]. 

With this in mind, we can write: 

$$\large\tag{1}
\mathbf{A}\mathbf{x} = T \mathbf{x} = f(\mathbf{x})
$$

and understand that they are all the same. A matrix is a linear map is a function moving vectors between [[Vector Spaces]].



## Related
[[Vector Spaces]]
[[Fundamental Linear Maps]] 
[[Geometry of Linear Algebra]]
[[Vector Independence]]
[[Linear Algebra]] `Deisenroth summmary of chapter 3`
[[Matrix Definitions]]




## References

> [!PDF|yellow] [[Thomas2018.pdf#page=8&selection=300,0,318,1&color=yellow|Thomas2018, p.8]]
> > That is, the jth column of A consists of the coordinates of T vj in the chosen basis for W .
> 
> 

> [!PDF|yellow] [[Thomas2018.pdf#page=8&selection=319,0,344,8&color=yellow|Thomas2018, p.8]]
> > Conversely, every matrix A ∈ Rm×n induces a linear map T : Rn → Rm given by

