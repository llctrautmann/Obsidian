---
title: Vector Calculus
date:
  - 02-04-2024
time: 17:03
author: Luca Trautmann
tags:
  - Mathematics
series: M4ML
chapter: 5
status: Incomplete
modified: 2024-09-17
---
> A function f is a quantity that relates two quantities to each other. In this book, these quantities are typically inputs x ∈ RD and targets (function values) $f(x)$, which we assume are real-valued if not stated otherwise. (Deisenroth et al., 2020, p. 139)

# Vector Calculus
## Defining a function
I want to start with a simple definition of a function: 

$$
\begin{align}
f: \mathbb{R}^D &\to \mathbb{R} \\
\boldsymbol{x} &\mapsto f(\boldsymbol{x})
\end{align}
$$

For example, the dot product can be defined as a function. 

$$
\begin{aligned}
f: \mathbb{R}^2 & \rightarrow \mathbb{R} \\
\boldsymbol{x} & \mapsto x_1^2+x_2^2 .
\end{aligned}
$$

## Differentiation of Univariate Functions
We want to derive the derivative from first principles. The task is to find the slope of the secant through two points with the difference quotient: 

$$
\frac{\delta y}{\delta x}:=\frac{f(x+\delta x)-f(x)}{\delta x}
$$

with ever smaller distances of the two points, ergo as $\delta x$ gets infinitely small we get (with $\delta x= h$) the tangent at the point x, if $f$ is differentiable. The tangent is then the derivative of $f$ at $x$.

$$
\frac{\mathrm{d} f}{\mathrm{~d} x}:=\lim _{h \rightarrow 0} \frac{f(x+h)-f(x)}{h}
$$

`Note: The derivative of f points in the direction of the steepest ascent of f.`



## Taylor Series: Function Approximation
The Taylor series represents a function at a point as an infinite series of polynomials:

$$
T_n(x):=\sum_{k=0}^n \frac{f^{(k)}\left(x_0\right)}{k !}\left(x-x_0\right)^k
$$


## Basic Differentiation Rule

Product rule: $\quad(f(x) g(x))^{\prime}=f^{\prime}(x) g(x)+f(x) g^{\prime}(x)$

Quotient rule: $\quad\left(\frac{f(x)}{g(x)}\right)^{\prime}=\frac{f^{\prime}(x) g(x)-f(x) g^{\prime}(x)}{(g(x))^2}$

Sum rule: $\quad(f(x)+g(x))^{\prime}=f^{\prime}(x)+g^{\prime}(x)$

Chain rule: $\quad(g(f(x)))^{\prime}=(g \circ f)^{\prime}(x)=g^{\prime}(f(x)) f^{\prime}(x)$

Here, $g \circ f$ denotes function composition $x \mapsto f(x) \mapsto g(f(x))$.


## Partial Differentiation and Gradients
The generalisation of the derivative to functions of multiple variables is the gradient. To obtain the gradient, I need to build the partial derivatives wrt. to each variable in the function while keeping all other variables constant.

$$
\begin{aligned}
\frac{\partial f}{\partial x_1} & =\lim _{h \rightarrow 0} \frac{f\left(x_1+h, x_2, \ldots, x_n\right)-f(\boldsymbol{x})}{h} \\
& \vdots \\
\frac{\partial f}{\partial x_n} & =\lim _{h \rightarrow 0} \frac{f\left(x_1, \ldots, x_{n-1}, x_n+h\right)-f(\boldsymbol{x})}{h}
\end{aligned}
$$

Or in a more compact form:

$$\large
\nabla_{\boldsymbol{x}} f=\operatorname{grad} f=\frac{\mathrm{d} f}{\mathrm{~d} \boldsymbol{x}}=\left[\begin{array}{llll}
\frac{\partial f(\boldsymbol{x})}{\partial x_1} & \frac{\partial f(\boldsymbol{x})}{\partial x_2} & \cdots & \frac{\partial f(\boldsymbol{x})}{\partial x_n}
\end{array}\right] \in \mathbb{R}^{1 \times n}
$$

This row vector is called the **gradient** of f or the [[Jacobian]] and is the generalisation of the derivative for single variables.  

`There is something missing here (145 - 149 Deisenroth)`

## Basic Rules for Partial Differentiation

- Product Rule: $\frac{\partial}{\partial \boldsymbol{x}}(f(\boldsymbol{x}) g(\boldsymbol{x}))=\frac{\partial f}{\partial \boldsymbol{x}} g(\boldsymbol{x})+f(\boldsymbol{x}) \frac{\partial g}{\partial \boldsymbol{x}}$

- Sum Rule: $\frac{\partial}{\partial \boldsymbol{x}}(f(\boldsymbol{x})+g(\boldsymbol{x}))=\frac{\partial f}{\partial \boldsymbol{x}}+\frac{\partial g}{\partial \boldsymbol{x}}$

- Chain Rule: $\frac{\partial}{\partial \boldsymbol{x}}(g \circ f)(\boldsymbol{x})=\frac{\partial}{\partial \boldsymbol{x}}(g(f(\boldsymbol{x})))=\frac{\partial g}{\partial f} \frac{\partial f}{\partial \boldsymbol{x}}$


## Chain Rule




$$\large
\frac{\mathrm{d} f}{\mathrm{~d} t}=\left[\begin{array}{ll}
\frac{\partial f}{\partial x_1} & \frac{\partial f}{\partial x_2}
\end{array}\right]\left[\begin{array}{l}
\frac{\partial x_1(t)}{\partial t} \\
\frac{\partial x_2(t)}{\partial t}
\end{array}\right]=\frac{\partial f}{\partial x_1} \frac{\partial x_1}{\partial t}+\frac{\partial f}{\partial x_2} \frac{\partial x_2}{\partial t}
$$

For multivariable function the same rule applies but it returns the partial derivatives

$$\large
\begin{aligned}
& \frac{\partial f}{\partial s}=\frac{\partial f}{\partial x_1} \frac{\partial x_1}{\partial s}+\frac{\partial f}{\partial x_2} \frac{\partial x_2}{\partial s} \\
& \frac{\partial f}{\partial t}=\frac{\partial f}{\partial x_1} \frac{\partial x_1}{\partial t}+\frac{\partial f}{\partial x_2} \frac{\partial x_2}{\partial t}
\end{aligned} \tag{1}
$$

I can rewrite this as a handy matrix notation:
$$\large
\frac{\mathrm{d} f}{\mathrm{~d}(s, t)}=\frac{\partial f}{\partial \boldsymbol{x}} \frac{\partial \boldsymbol{x}}{\partial(s, t)}=\underbrace{\left[\begin{array}{ll}
\frac{\partial f}{\partial x_1} & \frac{\partial f}{\partial x_2}
\end{array}\right]}_{=\frac{\partial f}{\partial \boldsymbol{x}}} \underbrace{\left[\begin{array}{ll}
\frac{\partial x_1}{\partial s} & \frac{\partial x_1}{\partial t} \\
\frac{\partial x_2}{\partial s} & \frac{\partial x_2}{\partial t}
\end{array}\right]}_{=\frac{\partial \boldsymbol{x}}{\partial(s, t)}} .
$$
where the first matrix multiplication gives line one in (1) and the second matrix multiplication gives the second line in (1). 
`Check hand written notes to see that this actually holds`

## Gradients of Vector-Values Functions

> [!def] 
> For a function $\boldsymbol{f}: \mathbb{R}^n \rightarrow \mathbb{R}^m$ and a vector $\boldsymbol{x}=\left[x_1, \ldots, x_n\right]^{\top} \in \mathbb{R}^n$, the corresponding vector of function values is given as
> $$
> \boldsymbol{f}(\boldsymbol{x})=\left[\begin{array}{c}
> f_1(\boldsymbol{\left[x_1, \ldots, x_n\right]}) \\
> \vdots \\
> f_m(\boldsymbol{\left[x_1, \ldots, x_n\right]})
> \end{array}\right] \in \mathbb{R}^m
> $$
> This means that the vector function is a vector of functions. This is also referred to as a vector-valued function and can be thought of a vector that contains multiple scalar valued functions. 


The extension of the partial derivatives for all values in $\left[x_1, \ldots, x_n\right]$ is the [[Jacobian]]. Which gives matrix of the partial derivatives with the values of x as the column dimension and the functions as the row dimensions.

$$\large
\begin{aligned}
\frac{\mathrm{d} \boldsymbol{f}(\boldsymbol{x})}{\mathrm{d} \boldsymbol{x}}&=\left[\frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial x_1} \cdots \frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial x_n}\right] \\
& =\left[\begin{array}{c|c|c}
\frac{\partial f_1(\boldsymbol{x})}{\partial x_1} & \cdots & \frac{\partial f_1(\boldsymbol{x})}{\partial x_n} \\
\vdots \\
\frac{\partial f_m(\boldsymbol{x})}{\partial x_1} & \cdots & \frac{\partial f_m(\boldsymbol{x})}{\partial x_n}
\end{array}\right] \in \mathbb{R}^{m \times n} \\
&
\end{aligned}
$$
I can write this in a more generalised form as:
$$\large 
\begin{aligned}
\boldsymbol{J}&=\nabla_{\boldsymbol{x}} \boldsymbol{f}=\frac{\mathrm{d} \boldsymbol{f}(\boldsymbol{x})}{\mathrm{d} \boldsymbol{x}}=\left[\begin{array}{lll}
\frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial x_1} & \ldots & \frac{\partial \boldsymbol{f}(\boldsymbol{x})}{\partial x_n}
\end{array}\right] \\
& =\left[\begin{array}{ccc}
\frac{\partial f_1(\boldsymbol{x})}{\partial x_1} & \cdots & \frac{\partial f_1(\boldsymbol{x})}{\partial x_n} \\
\vdots & & \vdots \\
\frac{\partial f_m(\boldsymbol{x})}{\partial x_1} & \cdots & \frac{\partial f_m(\boldsymbol{x})}{\partial x_n}
\end{array}\right], \\
\boldsymbol{x}&=\left[\begin{array}{c}
x_1 \\
\vdots \\
x_n
\end{array}\right], \quad J(i, j)=\frac{\partial f_i}{\partial x_j} \\
&
\end{aligned}
$$

### Hessian Matrix
The Hessian is the extension of the [[Jacobian]] to higher order derivatives.