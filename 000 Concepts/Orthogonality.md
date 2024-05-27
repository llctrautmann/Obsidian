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
# Orthogonality
## Purpose
[[Inner Products|Inner products]] also introduce calculations of angles into vector spaces. 

$$\large\tag{1}
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\|\boldsymbol{x}\|\|\boldsymbol{y}\|} .
$$

The Cauchy-Schwarz Inequality allows this deconstruction: 

$$\large\tag{2}
\cos \omega=\frac{\langle\boldsymbol{x}, \boldsymbol{y}\rangle}{\sqrt{\langle\boldsymbol{x}, \boldsymbol{x}\rangle\langle\boldsymbol{y}, \boldsymbol{y}\rangle}}
$$