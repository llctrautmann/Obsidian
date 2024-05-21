---
title: Jacobian
date:
  - 19-03-2024
time: 09:53
author: Luca Trautmann
tags: 
series: M4ML
chapter: 999
status: Incomplete
modified: 2024-03-19
---
# Jacobian
The Jacobian is just the derivative for vector functions.
$$
J_f=\frac{\partial f}{\partial x}=\left[\begin{array}{c}
\nabla f_1^{\top} \\
\vdots \\
\nabla f_{n_f}^{\top}
\end{array}\right]=\underbrace{\left[\begin{array}{ccc}
\frac{\partial f_1}{\partial x_1} & \cdots & \frac{\partial f_1}{\partial x_{n_x}} \\
\vdots & \ddots & \vdots \\
\frac{\partial f_{n_f}}{\partial x_1} & \cdots & \frac{\partial f_{n_f}}{\partial x_{n_x}}
\end{array}\right]}_{\left(n_f \times n_x\right)}
$$
- $n_f$ is the number of outputs of the function
- $n_{x}$ is the number of inputs into the function









