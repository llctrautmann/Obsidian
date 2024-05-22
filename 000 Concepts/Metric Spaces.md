---
title: Metric Spaces
date:
  - 17-05-2024
time: 22:49
author: Luca Trautmann
tags:
  - LinAlg
  - AnalyticGeometry
series: Linear Algebra
chapter: 
status: Incomplete
modified: 2024-05-22
---
# Metric Spaces
A metric space is a set with a defined [metric](Metrics). But unlike a [space with a defined norm](Normed%20Space), a metric space is not necessarily a [vector space](Vector%20Spaces). To be a metric space, only the conditions of the metric space need to be fulfilled: 

## Conditions
A set $M$ with a metric $d$ is a metric space if $d: M \times M \to \mathbb{R}$ satisfies the following properties $\forall x, \forall y, \forall z \in M$:
  1. $d(x, y) \geq 0$ (non-negativity)
  2. $d(x, y) = 0$ if and only if $x = y$ (identity of indiscernibles)
  3. $d(x, y) = d(y, x)$ (symmetry)
  4. $d(x, z) \leq d(x, y) + d(y, z)$ (triangle inequality)


## Usefulness
This is not a complete picture but metric spaces allow for limits to be calculated for non-number mathematical objects such as functions. 

# References

> [!PDF|yellow] [[Thomas2018.pdf#page=9&selection=261,0,262,19&color=yellow|Thomas2018, p.9]]
> > A key motivation for metrics is that they allow limits to be defined for mathematical objects other than real numbers. 
> 
> 