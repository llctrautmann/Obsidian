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
modified: 2024-04-02
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
The generalization of the derivative to functions of several variables is the gradient. To obtain the gradient, I need to build the partial derivatives wrt. to each variable in the function while keeping all other variables constant.

$$
\begin{aligned}
\frac{\partial f}{\partial x_1} & =\lim _{h \rightarrow 0} \frac{f\left(x_1+h, x_2, \ldots, x_n\right)-f(\boldsymbol{x})}{h} \\
& \vdots \\
\frac{\partial f}{\partial x_n} & =\lim _{h \rightarrow 0} \frac{f\left(x_1, \ldots, x_{n-1}, x_n+h\right)-f(\boldsymbol{x})}{h}
\end{aligned}
$$
Or in a more compact form:

$$
\nabla_{\boldsymbol{x}} f=\operatorname{grad} f=\frac{\mathrm{d} f}{\mathrm{~d} \boldsymbol{x}}=\left[\begin{array}{llll}
\frac{\partial f(\boldsymbol{x})}{\partial x_1} & \frac{\partial f(\boldsymbol{x})}{\partial x_2} & \cdots & \frac{\partial f(\boldsymbol{x})}{\partial x_n}
\end{array}\right] \in \mathbb{R}^{1 \times n}
$$
