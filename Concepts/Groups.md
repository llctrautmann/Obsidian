---
title: Groups
date:
  - 03-05-2024
time: 18:23
author: Luca Trautmann
tags: 
series: Mathematics
chapter: Auxillary
status: Incomplete
modified: 2024-05-03
---
# Groups
A group is a set of elements and an operation defined on these elements that keeps some structure of the set intact. 

## Conditions
 __Group__. Consider a set $\mathcal{G}$ and an operation $\otimes: \mathcal{G} \times \mathcal{G} \rightarrow \mathcal{G}$ defined on $\mathcal{G}$. Then $G:=(\mathcal{G}, \otimes)$ is called a group if the following hold:

1. Closure of $\mathcal{G}$ under $\otimes: \forall x, y \in \mathcal{G}: x \otimes y \in \mathcal{G}$ `\\ Stays the same kind`
2. Associativity: $\forall x, y, z \in \mathcal{G}:(x \otimes y) \otimes z=x \otimes(y \otimes z)$ 
3. Neutral element: $\exists e \in \mathcal{G} \forall x \in \mathcal{G}: x \otimes e=x$ and $e \otimes x=x$ `\\ 1 for example`
4. Inverse element: $\forall x \in \mathcal{G} \exists y \in \mathcal{G}: x \otimes y=e$ and $y \otimes x=e$, where $e$ is the neutral element. We often write $x^{-1}$ to denote the inverse element of $x$. 

Note: The inverse element is defined wrt the operation not the element and does not necessarily mean $\frac{1}{x}$. 

__Abelian Group__: If additionally $\forall x, y \in \mathcal{G}: x \otimes y=y \otimes x$, then $G=(\mathcal{G}, \otimes)$ is an Abeliar group (commutative).

__General Linear Group__: The set of regular (invertible) matrices $\boldsymbol{A} \in \mathbb{R}^{n \times n}$ is a group with respect to matrix multiplication is called general linear group $G L(n, \mathbb{R})$. However, since matrix multiplication is not commutative, the group is not Abelian.
