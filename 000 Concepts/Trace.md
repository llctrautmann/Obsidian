---
title: Trace
date:
  - 26-05-2024
time: 18:45
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
status: Incomplete
type: 
formula: 
🍙: いや
modified: 2024-05-27
---
# Trace
## Definition
The trace of a square matrix is the sum of its diagonal entries:
$$\large\tag{1}
\operatorname{tr}(\mathbf{A})=\sum_{i=1}^n A_{i i}
$$


## Properties
1. $\operatorname{tr}(\mathbf{A}+\mathbf{B})=\operatorname{tr}(\mathbf{A})+\operatorname{tr}(\mathbf{B})$
2. $\operatorname{tr}(\alpha \mathbf{A})=\alpha \operatorname{tr}(\mathbf{A})$
3. $\operatorname{tr}\left(\mathbf{A}^{\top}\right)=\operatorname{tr}(\mathbf{A})$
4. $\operatorname{tr}(\mathbf{A B C D})=\operatorname{tr}(\mathbf{B C D A})=\operatorname{tr}(\mathbf{C D A B})=\operatorname{tr}(\mathbf{D A B C})$

- $(4)$ is called `invariance under cyclic permutations`
- 

## Noteworthy
Most interestingly there is a connection to [[Eigenthings|eigenvalues]]. The trace is the sum of the eigenvalues. []

$$\large\tag{2}
\operatorname{tr}(\mathbf{A})=\sum_i \lambda_i(\mathbf{A})
$$




# References
> [!PDF|yellow] [[Thomas2018.pdf#page=16&selection=28,0,29,14&color=yellow|Thomas2018, p.16]]
> > Interestingly, the trace of a matrix is equal to the sum of its eigenvalues (repeated according to multiplicity):

> [!PDF|yellow] [[murphy2022.pdf#page=282&selection=318,0,318,81&color=yellow|murphy2022, p.252]]
> > The eigenvalues of a diagonal or triangular matrix are just the diagonal entries.

