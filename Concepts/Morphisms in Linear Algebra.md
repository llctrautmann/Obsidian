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
modified: 2024-05-14
---
> [!PDF|yellow] [[deisenroth2020.pdf#page=54&selection=250,8,251,63&color=yellow|deisenroth2020, p.48]]
> > When working with matrices, we have to keep in mind what the matrix represents: a linear mapping or a collection of vectors.


# Morphisms in Linear Algebra

[ADD GENERAL INTRODUCTION]

## Injective, Surjective, Bijective
Consider a mapping $\Phi: V \to W$. Then $\Phi$ is called:

1) Injective: if $\forall \boldsymbol{x}, \boldsymbol{y} \in \mathcal{V}: \Phi(\boldsymbol{x}) = \Phi (\boldsymbol{y}) \Longrightarrow \boldsymbol{x} = \boldsymbol{y}$ 
`Each element of the domain maps to a unique element in the codomain; also known as one-to-one`

2) Surjective: if $\Phi(\mathcal{V})=\mathcal{W}$ 
`all elements in W can be reached from V; Range = Codomain; covering the entire space`

3) Bijective: if it is Injective and Surjective



<mark class="hltr-red">NOTE</mark>: A bijective linear mapping can be undone with the inverse $\Phi^{-1}$. For visualisation hover: [here](injective_surjective.png)


## Vector Space Homomorphism, Isomorphism
In algebraic terms, a linear map or linear transformation can also be called a vector space homomorphism or homomorphism of vector spaces. An invertible homomorphism (where the inverse is also a homomorphism) is called an isomorphism. In concrete terms a linear transformation is always a matrix.

`Think about loss of information; isomorphism means all data points are mapped uniquely, so no information is lost and the structure of the vector space is the same.`  

There are two conditions:
$$
\forall \boldsymbol{x}, \boldsymbol{y} \in V \forall \lambda, \psi \in \mathbb{R}: \Phi(\lambda \boldsymbol{x}+\psi \boldsymbol{y})=\lambda \Phi(\boldsymbol{x})+\psi \Phi(\boldsymbol{y})
$$

- Closure under addition related to associativity ([[Vector Spaces#Associativity]])
- Closure under scalar multiplication related to distributivity ([[Vector Spaces#Distributivity]])

`fundamentally it is always important with vector spaces to keep the two properties/closure conditions under consideration.`

## Special Linear Mappings
















__Iso-, Endo-, Automorphism__. The definitions for Iso-, Endo-, Automorphism are as follows:

- Isomorphism: $\Phi: V \to W$ linear and bijective 

A linear map $T$ is called an isomorphism if the following two conditions are satisfied.
- $T$ is one to one. That is, if $T(\vec{x})=T(\vec{y})$, then $\vec{x}=\vec{y}$.
- $T$ is onto. That is, if $\vec{w} \in W$, there exists $\vec{v} \in V$ such that $T(\vec{v})=\vec{w}$.

Two such subspaces which have an isomorphism as described above are said to be isomorphic. 

We can also derive that [[Vector Spaces]] and [[Subspaces]] with the same dimensionality with the same [[Vector Space Dimensionality]] will be isomorphic. 


## References

> [!PDF|yellow] [[Thomas2018.pdf#page=8&selection=45,2,71,1&color=yellow|Thomas2018, p.8]]
> > If there exists an isomorphism from $V$ to $W$, then $V$ and $W$ are said to be isomorphic, and we write $V \cong W$. 

> [!PDF|yellow] [[Thomas2018.pdf#page=8&selection=73,2,74,64&color=yellow|Thomas2018, p.8]]
> > Isomorphic vector spaces are essentially “the same” in terms of their algebraic structure


## GPT (incorporate and del)
Yes, any invertible matrix represents an isomorphism between vector spaces of the same dimension.

Let's break it down:

1. **Invertible Matrix**: A matrix \( A \) is invertible if there exists another matrix, typically denoted as \( A^{-1} \), such that \( AA^{-1} = A^{-1}A = I \), where \( I \) is the identity matrix.

2. **Isomorphism**: An isomorphism between vector spaces \( V \) and \( W \) is a linear transformation \( T: V \rightarrow W \) that is bijective, meaning it's both injective (one-to-one) and surjective (onto).

Now, here's how an invertible matrix is related to an isomorphism:

- Let's say you have a vector space \( V \) with basis \( \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \).
  
- Applying an invertible matrix \( A \) to \( V \) gives you a new vector space \( W = A(V) \).

- The columns of \( A \) represent where each basis vector of \( V \) is mapped to in \( W \). Since \( A \) is invertible, its columns form a basis for \( W \).

- Since \( A \) is invertible, there exists a matrix \( A^{-1} \) such that \( A^{-1}A = I \). This means that \( A^{-1} \) "undoes" the transformation of \( A \).

- Therefore, \( A^{-1} \) maps vectors in \( W \) back to vectors in \( V \).

So, \( A \) represents an isomorphism between \( V \) and \( W \), and \( A^{-1} \) represents the inverse isomorphism from \( W \) back to \( V \).

In summary, any invertible matrix represents an isomorphism because it's a bijective linear transformation between two vector spaces of the same dimension.