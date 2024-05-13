---
title: Morphisms in Linear Algebra
date:
  - 13-05-2024
time: 10:47
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-13
---
# Morphisms in Linear Algebra
## Injective, Surjective, Bijective
Consider a mapping $\Phi: V \to W$. Then $\Phi$ is called:

1) Injective: if $\forall \boldsymbol{x}, \boldsymbol{y} \in \mathcal{V}: \Phi(\boldsymbol{x}) = \Phi (\boldsymbol{y}) \Longrightarrow \boldsymbol{x} = \boldsymbol{y}$ 
`Each element of the domain maps to a unique element in the codomain; also known as one-to-one`

2) Surjective: if $\Phi(\mathcal{V})=\mathcal{W}$ 
`all elements in W can be reached from V; Range = Codomain; covering the entire space`

3) Bijective: if it is Injective and Surjective

<mark class="hltr-red">NOTE</mark>: A bijective linear mapping can be undone with the inverse $\Phi^{-1}$. 


## Homomorphism, Isomorphism
In algebraic terms, a linear map is called a homomorphism of vector spaces. An invertible homomorphism (where the inverse is also a homomorphism) is called an isomorphism. 

`Think about loss of information; isomorphism means all data points are mapped uniquely, so no information is lost.`  





> [!PDF|yellow] [[Thomas2018.pdf#page=8&selection=45,2,71,1&color=yellow|Thomas2018, p.8]]
> > If there exists an isomorphism from $V$ to $W$, then $V$ and $W$ are said to be isomorphic, and we write $V \cong W$.  


> [!PDF|yellow] [[Thomas2018.pdf#page=8&selection=73,2,74,64&color=yellow|Thomas2018, p.8]]
> > Isomorphic vector spaces are essentially “the same” in terms of their algebraic structure


__Iso-, Endo-, Automorphism__. The definitions for Iso-, Endo-, Automorphism are as follows:

- Isomorphism: $\Phi: V \to W$ linear and bijective 

A linear map $T$ is called an isomorphism if the following two conditions are satisfied.
- $T$ is one to one. That is, if $T(\vec{x})=T(\vec{y})$, then $\vec{x}=\vec{y}$.
- $T$ is onto. That is, if $\vec{w} \in W$, there exists $\vec{v} \in V$ such that $T(\vec{v})=\vec{w}$.

Two such subspaces which have an isomorphism as described above are said to be isomorphic. 

We can also derive that [[Vector Spaces]] and [[Subspaces]] with the same dimensionality with the same [[Vector Space Dimensionality]] will be isomorphic. 