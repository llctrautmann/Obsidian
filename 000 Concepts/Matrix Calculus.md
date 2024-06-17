---
title: Matrix Calculus
date:
  - 17-06-2024
time: 12:08
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: 
formula: 
aliases:
  - gradient
  - Gradient
  - Derivatives
  - derivative
  - o
modified: 2024-06-17
---
- [ ] _Expand this secttion with [[parr2018.pdf]]_ 

# Matrix Calculus

We are fundamentally dealing with rate of change in calculus[^1]. 

## Derivatives
his measures how quickly the output changes when we move a small distance in input space away from x [^2].
$$ \Large\tag{1}
f^{\prime}(x) \triangleq \lim _{h \rightarrow 0} \frac{\int(x+h)-f(x)}{h}
$$

- In the classical understanding the derivative is the slope of the tangent at the point. 
- In line with [[Norms in Linear Algebra|norms]], or [[Metrics]] the derivative is also a mapping
	- linking functions to functions: $\large D(f)=f'$ [^3] 
	- Leibnitz notation: $\frac{d y}{d x}$ 

## Gradients
Gradients are the extension of the derivative to vector functions [^4]. The gradient is then just the set of partial derivatives stacked. 

$$ \large\tag{2}
\frac{\partial f}{\partial x_i}=\lim _{h \rightarrow 0} \frac{f\left(\boldsymbol{x}+h \boldsymbol{e}_i\right)-f(\boldsymbol{x})}{h}
$$
- $\mathbf{e}_{i}$ is the basis vector 

This results in the $\large\nabla$: 
$$ \large\tag{3} 
\boldsymbol{g}=\frac{\partial f}{\partial \boldsymbol{x}}=\nabla f=\left(\begin{array}{c}
\frac{\partial f}{\partial x_1} \\
\vdots \\
\frac{\partial f}{\partial x_n}
\end{array}\right)
$$

- In case of a vector function the gradient describes a **vector field**, for scalar functions a **scalar field**
## Directional Derivatives
The directional derivative is the change of a unit vector when moving along the function. It is the inner product between the gradient and the unit vector [^5]. 

$$ \large\tag{4}
D_v f(\boldsymbol{x})=\nabla f(\boldsymbol{x}) \cdot \boldsymbol{v}
$$
- $\boldsymbol{v}$ is the normalised[^6] vector. 
## Total Derivatives
- The total derivative gives me the rate of change for composite functions that both depend on a variable (such as time) [^7]. 

## [[Jacobian]]
### Jacobians and vectors
### Jacobian of a composition








## Hessian 

# Footnotes

[^1]: [[murphy2022.pdf#page=297&selection=210,0,216,41&color=yellow|murphy2022, p.267]] 
[^2]: [[murphy2022.pdf#page=297&selection=282,28,285,1&color=yellow|murphy2022, p.267]] 
[^3]: [[murphy2022.pdf#page=298&selection=141,2,166,47&color=yellow|murphy2022, p.268]]
[^4]: $f:\mathbb{R}^n\rightarrow \mathbb{R}$
[^5]: [[murphy2022.pdf#page=299&selection=26,0,37,1&color=yellow|murphy2022, p.269]]
[^6]: Note: Normalisation Formula: $\mathbf{u}=\frac{\mathbf{v}}{\|\mathbf{v}\|}=\left(\frac{v_1}{\sqrt{\sum_{i=1}^n v_i^2}}, \frac{v_2}{\sqrt{\sum_{i=1}^n v_i^2}}, \ldots, \frac{v_n}{\sqrt{\sum_{i=1}^n v_i^2}}\right)$
[^7]: [[murphy2022.pdf#page=299&selection=63,0,63,18&color=yellow|murphy2022, p.269]] 