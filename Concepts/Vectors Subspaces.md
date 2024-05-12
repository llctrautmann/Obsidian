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
modified: 2024-05-12
---

> [!PDF|yellow] [[Thomas2018.pdf#page=7&selection=184,0,184,90&color=yellow|Thomas2018, p.7]]
> > As a concrete example, a line passing through the origin is a subspace of Euclidean space.


# Vectors Subspaces

Subspaces are more limited spaces within existing vectors spaces. For example, if I transform a larger space into a lower dimensional space, the [[Null Space]] is the space that contain all the vectors that are $\mathbf{0}$ in the new vector space. 

$$
S \subseteq V
$$

## Rules for Subspaces

1. Must contain $\mathbf{0}$ 

`This is a direct consequence of` [[Vector Spaces#Additive Identity]]`needing to contain the zero element so that` $x+0=x$ `holds`.

2. $S$ needs to be closed under addition. 

`This relates to the fundamental principle of an algebra` [[Linear Algebra#What is an algebra?]]. `We need to stay the same element.` 

3. Closed under scalar multiplication: 
$$\mathbf{x} \in S, \alpha \in \mathbb{R}$$ therefore. $$\alpha \mathbf{x} \in S$$

`same as 2.`  

##### Note:
*Mentally there is some connection to [[Notes on Probability Theory#Sigma Algebras]]. I do not want to work with things that behave pathologically mathematically in general.*


## Combining Subspaces
Subspaces can be combined:

$$
U+W=\{\mathbf{u}+\mathbf{w} \mid \mathbf{u} \in U, \mathbf{w} \in W\}
$$


If the intersection of the two subspaces is just $\left\{ \mathbf{0}\right \}$ it is called a **direct sum** $U \oplus W$. 

