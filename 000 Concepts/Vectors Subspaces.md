---
title: Vectors Subspaces
date:
  - 12-05-2024
time: 14:47
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-26
---

> [!PDF|yellow] [[Thomas2018.pdf#page=7&selection=184,0,184,90&color=yellow|Thomas2018, p.7]]
> > As a concrete example, a line passing through the origin is a subspace of Euclidean space.


# Vectors Subspaces

Subspaces are more limited spaces within an existing [[Vector Spaces]]. For example, if I transform a larger space into a lower dimensional space, the [[Null Space]] is the space that contain all the vectors that are $\mathbf{0}$ in the new vector space. 

$$
S \subseteq V
$$

## Rules for Subspaces

1. Must contain $\mathbf{0}$ 

`This is a direct consequence of` [[Vector Spaces#Additive Identity]]` and any vector space or subspace needing to contain the zero element so that` $x+0=x$ `holds`.

2. $S$ needs to be closed under addition. 

`This relates to the fundamental principle of an algebra` [[Linear Algebra#What is an algebra?]]. `We need to stay the same element.` 

3. Closed under scalar multiplication: 
$$\mathbf{x} \in S, \alpha \in \mathbb{R}$$ therefore. $$\alpha \mathbf{x} \in S$$

`same as 2.`  

##### Note:
*Mentally there is some connection to [[000 Background Probability Theory#Sigma Algebras]]. I do not want to work with things that behave pathologically mathematically in general.*





## Combining Subspaces
Subspaces can be combined:

$$
U+W=\{\mathbf{u}+\mathbf{w} \mid \mathbf{u} \in U, \mathbf{w} \in W\}
$$


If the intersection of the two subspaces is just $\left\{ \mathbf{0}\right \}$ it is called a **direct sum** $U \oplus W$. 

## Dimensionality of Combined Subspaces
[[Vector Space Dimensionality]] for combined vector spaces is given by. 

$$
\operatorname{dim}(U+W)=\operatorname{dim} U+\operatorname{dim} W-\operatorname{dim}(U \cap W)
$$

And for direct sums;

$$
\operatorname{dim}(U \oplus W)=\operatorname{dim} U+\operatorname{dim} W
$$

`This immidiately reminds me of` [[Probability Basics#Joint Probability]] `Its the same formula, so there is some interesting connection between the two. Maybe set theory is the underlying fabric. Vector spaces are groups, groups are sets and so this is all fundamentally connected with each other.` 

## Special Subspaces

1) [[Column Space]]
2) [[Null Space]]
3) [[Row Space]] 

