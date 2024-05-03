---
title: Subspaces
date:
  - 03-05-2024
time: 21:26
author: Luca Trautmann
tags:
  - "#LinAlg"
series: Linear Algebra
chapter: "9"
status: Incomplete
modified: 2024-05-03
---
# Subspaces
[[Vector Spaces]] can contain smaller spaces that do follow all rules necessary for being their own space. Important examples are the: 

1) [[Column Space]]
2) [[Null Space]]
3) [[Row Space]] 

Vector spaces can contain other vector spaces. If $V$ is a vector space, then $S \subseteq V$ is said to be a subspace of $V$ if

- (i) $\mathbf{0} \in S$
- (ii) $S$ is closed under addition: $\mathbf{x}, \mathbf{y} \in S$ implying $\mathbf{x}+\mathbf{y} \in S$
- (iii) $S$ is closed under scalar multiplication: $\mathbf{x} \in S, \alpha \in \mathbb{R}$ implies $\alpha \mathbf{x} \in S$

> [!PDF|yellow] [[@Thomas2018.pdf#page=7&selection=71,0,73,0&color=yellow|@Thomas2018, p.7]]
> > Euclidean space is used to mathematically represent physical space, with notions such as distance, length, and angles.