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
modified: 2024-05-27
---
# Angles
## Purpose
[[Inner Products|Inner products]] also introduce calculations of angles into vector spaces. 

$$\large\tag{1}
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\|\boldsymbol{x}\|\|\boldsymbol{y}\|} .
$$

This is deconstructed into: 

$$\large\tag{2}
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\sqrt{\langle\boldsymbol{x}, \boldsymbol{x}\rangle\langle\boldsymbol{y}, \boldsymbol{y}\rangle}}
$$

## Orthogonality

$$\langle\boldsymbol{x}, \boldsymbol{y}\rangle=0$$

## Orthogonal Matrix

$$
\mathbf{Q}^{\top} \mathbf{Q}=\mathbf{Q}^{\top}=\mathbf{I}
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

# References

> [!PDF|yellow] [[Thomas2018.pdf#page=16&selection=220,10,221,68&color=yellow|Thomas2018, p.16]]
> > multiplication by an orthogonal matrix can be considered as a transformation that preserves length, but may rotate or reflect the vector about the origin.
> 
> 