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
modified: 2024-06-12
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
Most interestingly there is a connection to [[Eigenthings|eigenvalues]]. The trace is the sum of the eigenvalues. [^1]

$$\large\tag{2}
\operatorname{tr}(\mathbf{A})=\sum_i \lambda_i(\mathbf{A})
$$
For diagonal matrices that is especially simple as the eigenvalue are just the values on the diagonal [^2]

## Trace Trick
The trace trick $\boldsymbol{x}^{\top} \mathbf{A} \boldsymbol{x}=\operatorname{tr}\left(\boldsymbol{x}^{\top} \mathbf{A} \boldsymbol{x}\right)=\operatorname{tr}\left(\boldsymbol{x} \boldsymbol{x}^{\top} \mathbf{A}\right)$ is a neat trick that can make some calculations cheaper, if it is particularly expensive to evaluate the matrix $\mathbf{A}$[^3].
	- $\operatorname{tr}(\mathbf{A})=\operatorname{tr}\left(\mathbf{A} \mathbb{E}\left[v v^{\top}\right]\right)=\mathbb{E}\left[\operatorname{tr}\left(\mathbf{A} v v^{\top}\right)\right]=\mathbb{E}\left[\operatorname{tr}\left(v^{\top} \mathbf{A} v\right)\right]=\mathbb{E}\left[v^{\top} \mathbf{A} v\right]$ is the hutchinson trace estimation. 


# Footnotes

[^1]: [[Thomas2018.pdf#page=16&selection=28,0,29,14&color=yellow|Thomas2018, p.16]]
[^2]: [[murphy2022.pdf#page=282&selection=318,0,318,81&color=yellow|murphy2022, p.252]]
[^3]: [[murphy2022.pdf#page=264&selection=313,0,323,9&color=yellow|murphy2022, p.234]] 