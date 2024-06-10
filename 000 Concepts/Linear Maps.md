---
title: Linear Maps
date:
  - 03-05-2024
time: 18:51
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: "8"
status: Incomplete
modified: 2024-06-10
aliases:
  - linear map
  - linear maps
  - bilinear map
formula: $T:V \rightarrow W$
---
# Linear Maps
## Definition

Linear Maps are matrices are [[Functions]] that connect [[Vector Spaces]] (here $V$ and $W$)

$$\large\tag{1}
T:V \rightarrow W
$$

## Condition
To be valid a linear map needs to follow associativity and distributivity (or more precise: closure under addition and scalar multiplication). This is related to [[Vector Spaces#Conditions]] and a follows from the fundamental set theory of [[Groups]] and [[Morphisms in Linear Algebra]].

$$
\begin{aligned}
 T(\mathbf{x}+\mathbf{y}) &=T \mathbf{x}+T \mathbf{y} \\
 T(\alpha \mathbf{x}) &= \alpha T \mathbf{x} 
\end{aligned}
$$

> [!PDF|yellow] [[murphy2022.pdf#page=261&selection=136,0,200,0&color=yellow|murphy2022, p.231]]
> > A linear map or linear transformation is any function f : V → W such that $f(v + w) = f (v) + f (w)$ and $f (a v) = a f (v)$ for all $v, w ∈ V$
> 
> So we preserve addition and multiplication


## Noteworthy
The relationship between functions and linear maps is muddied by notational quirks. $\mathbf{Tx}=\mathbf{T}(\mathbf{x})$ holds, but mathematicians just want to make things more minimal. 




## Related
[[Geometry of Linear Algebra]] 
[[Moving between Dimensions]]
[[Morphisms in Linear Algebra]] (Most thoroughly explained)
