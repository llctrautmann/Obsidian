---
title: Orthogonality
date:
  - 27-05-2024
time: 13:19
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: Concept
formula: 
aliases:
  - orthogonality
  - orthogonal
modified: 2024-06-12
---
# Definition
- Two vectors $\boldsymbol{x}, \boldsymbol{y} \in \mathbb{R}^n$ are orthogonal if $\boldsymbol{x}^{\top} \boldsymbol{y}=0$.
- A vector $\boldsymbol{x} \in \mathbb{R}^n$ is normalized if $\|\boldsymbol{x}\|_2=1$. 
- A set of vectors that is pairwise orthogonal and normalized is called orthonormal.
- A square matrix $\mathrm{U} \in \mathbb{R}^{n \times n}$ is orthogonal if all its columns are orthonormal. (Note the different meaning of the term orthogonal when talking about vectors versus matrices.) 
	- If the entries of $\mathbf{U}$ are complex valued, we use the term unitary instead of orthogonal.[^1]

The main condition for any orthogonal matrix is $\mathbf{U}$ is orthonormal iff 

$$\large\tag{1}
\mathbf{U}^\top\mathbf{U}= \mathbf{I}=\mathbf{U}\mathbf{U}^\top
$$



# Angles
[[Inner Products|Inner products]] introduce calculations of angles into vector spaces. 

$$\large\tag{1}
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\|\boldsymbol{x}\|\|\boldsymbol{y}\|} .
$$

This is deconstructed into: 

$$\large\tag{2}
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\sqrt{\langle\boldsymbol{x}, \boldsymbol{x}\rangle\langle\boldsymbol{y}, \boldsymbol{y}\rangle}}
$$

Orthogonal matrics have the neat feature to preserve angles. 

$$\large\tag{3}
\cos (\alpha(\mathbf{U} x, \mathbf{U} y))=\frac{(\mathbf{U} x)^{\top}(\mathbf{U} y)}{\|\mathbf{U} x\| \mathbf{U} \boldsymbol{\|} \|}=\frac{\boldsymbol{x}^{\top} y}{\|x\|\|y \boldsymbol{d}\|}=\cos (\alpha(\boldsymbol{x}, \boldsymbol{y}))
$$

## Orthogonality

$$\langle\boldsymbol{x}, \boldsymbol{y}\rangle=0$$

## Orthogonal Matrix

$$
\mathbf{Q}^{\top} \mathbf{Q}=\mathbf{Q}\mathbf{Q}^{\top}=\mathbf{I}
$$

- maintains [[Inner Products|Inner products]] 

$$
(\mathbf{Q} \mathbf{x})^{\top}(\mathbf{Q} \mathbf{y})=\mathbf{x}^{\top} \mathbf{Q}^{\top} \mathbf{Q} \mathbf{y}=\mathbf{x}^{\top} \mathbf{I} \mathbf{y}=\mathbf{x}^{\top} \mathbf{y}
$$

- maintains [[Norms in Linear Algebra|norms]]:

$$
\|\mathbf{Q} \mathbf{x}\|_2=\sqrt{(\mathbf{Q} \mathbf{x})^{\top}(\mathbf{Q} \mathbf{x})}=\sqrt{\mathbf{x}^{\top} \mathbf{x}}=\|\mathbf{x}\|_2
$$

## Orthonormal

$$\langle\boldsymbol{x}, \boldsymbol{y}\rangle=0$$

$$
\|\boldsymbol{x}\|=1=\|\boldsymbol{y}\|
$$

- It is important to note, that a different [[Inner Products|inner product]] will yield a different answer. So orthonormality is determined by the type of [[Inner Products|inner product]].

## Noteworthy
- The Gram-Schmidt Technique allows the conversion of every square matrix into an orthogonal materix [^2]. 

# References

> [!PDF|yellow] [[Thomas2018.pdf#page=16&selection=220,10,221,68&color=yellow|Thomas2018, p.16]]
> > multiplication by an orthogonal matrix can be considered as a transformation that preserves length, but may rotate or reflect the vector about the origin.
> 
> 
# Footnotes

[^1]: [[murphy2022.pdf#page=269&selection=123,0,195,22&color=yellow|murphy2022, p.239]]
[^2]: [[murphy2022.pdf#page=270&selection=105,11,106,56&color=yellow|murphy2022, p.240]]