---
title: Projection
date:
  - 11-06-2024
time: 20:25
author: Luca Trautmann
tags:
  - LinAlg
series: Linear Algebra
🍙: いや
type: Concept
formula: $\mathbf{A}\left(\mathbf{A}^{\top} \mathbf{A}\right)^{-1} \mathbf{A}^{\top} \boldsymbol{y}$
aliases: 
modified: 2024-06-11
---
# Projection
## Definition
A projection is just the the vector that is closest to a target set (hyperplane, plane or line) measured by the Euclidean [[Norms in Linear Algebra|norm]]. 

This can be either: 

$$\frac{\mathbf{x} \cdot \mathbf{v}}{\mathbf{v}\cdot \mathbf{v}}$$ or alternatively: 
$$\operatorname{Proj}(\boldsymbol{y} ; \mathbf{A})=\operatorname{argmin}_{\boldsymbol{v} \in \mathcal{R}(\mathbf{A})}\|\boldsymbol{v}-\boldsymbol{y}\|_2=\mathbf{A}\left(\mathbf{A}^{\top} \mathbf{A}\right)^{-1} \mathbf{A}^{\top} \boldsymbol{y}$$

## Condition


## Noteworthy
- The equation for the projection $\mathbf{A}\left(\mathbf{A}^{\top} \mathbf{A}\right)^{-1} \mathbf{A}^{\top} \boldsymbol{y}$ is the normal equation used to solve linear regression problems. 