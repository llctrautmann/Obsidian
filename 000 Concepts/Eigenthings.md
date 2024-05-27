---
title: Eigenthings
date:
  - 26-05-2024
time: 00:02
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: 
formula: $$\mathbf{A}\mathbf{x}= \lambda \mathbf{x}$$
🍙: いや
aliases:
  - eigenvalues
  - eigenvectors
modified: 2024-05-27
---
# Eigenthings
## Description

Similar to [Inversions](Matrix%20Inversion) the first portion of this text will be restricted to square (real-valued) matrices. 

The basic formula is: 

$$\large\tag{1}
\mathbf{A}\mathbf{x}= \lambda \mathbf{x}
$$

So the eigenvalue is the scaling factor, while the eigenvector is the vector in the [vector space](Vector%20Spaces) that the [linear map](Linear%20Maps) $\mathbf{A}$ is applied to. 

The thing to remember is, if we apply $\mathbf{A}$, the vector orientation is the same but the scale/length (think about $\mid\mid\cdot\mid\mid$ -> [norm](Norms%20in%20Linear%20Algebra) here) is not. 


## Properties
1. Eigenvalues are infinitely scalable by a scalar, so $c\mathbf{u}$ is also an eigenvector. 
$$\large\tag{2}
\mathbf{A}(c \boldsymbol{u})=c \mathbf{A} \boldsymbol{u}=c \lambda \boldsymbol{u}=\lambda(c \boldsymbol{u})
$$


## Noteworthy
There are intricate connections to the [[Trace]] and the [[Determinant]]. 

The trace of a matrix is equal to the sum of its eigenvalues,
$$
\operatorname{tr}(\mathbf{A})=\sum_{i=1}^n \lambda_i .
$$

The determinant of $\mathbf{A}$ is equal to the product of its eigenvalues,
$$
\operatorname{det}(\mathbf{A})=\prod_{i=1}^n \lambda_i
$$

The rank of a [[Linear Maps|linear map]] $\mathbf{A}$ is equal to the number of non-zero eigenvalues. 
# References

> [!PDF|yellow] [[Thomas2018.pdf#page=15&selection=344,0,348,54&color=yellow|@Thomas2018, p.15]]
> > The trace of a square matrix is the sum of its diagonal entries:

> [!PDF|yellow] [[Thomas2018.pdf#page=15&selection=49,0,64,25&color=yellow|Thomas2018, p.15]]
> > For a square matrix A ∈ Rn×n, there may be vectors which, when A is applied to them, are **simply scaled by some constant**. 

> [!PDF|yellow] [[murphy2022.pdf#page=282&selection=6,0,21,1&color=yellow|murphy2022, p.252]]
> > Intuitively, this definition means that multiplying A by the vector u results in a new vector that points in the same direction as u, but is scaled by a factor λ.
> 
> seems to be the key, conceptually
