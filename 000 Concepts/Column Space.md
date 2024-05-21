---
title: Column Space
date:
  - 07-05-2024
time: 16:17
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-17
---
# Column Space

The columnspace of a matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$ is the  of its columns (considered as vectors in $\mathbb{R}^m$ ), and similarly the rowspace of $\mathbf{A}$ is the span of its rows (considered as vectors in $\mathbb{R}^n$ ). It is not hard to see that the columnspace of $\mathbf{A}$ is exactly the range of the linear map from $\mathbb{R}^n$ to $\mathbb{R}^m$ which is induced by $\mathbf{A}$, so we denote it by range $(\mathbf{A})$ in a slight abuse of notation. Similarly, the rowspace is denoted range $\left(\mathbf{A}^{\top}\right)$.


It is a remarkable fact that the dimension of the columnspace of $\mathbf{A}$ is the same as the dimension of the rowspace of $\mathbf{A}$. This quantity is called the $\operatorname{rank}$ of $\mathbf{A}$, and defined as
$$
\operatorname{rank}(\mathbf{A})=\operatorname{dim} \operatorname{range}(\mathbf{A})
$$


