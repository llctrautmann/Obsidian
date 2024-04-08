---
title: Super Resolution Problem Statement
date: 17-12-2023
time: 21:47
author: Luca Trautmann
tags:
  - Diffusion
series: Machine Learning Fundamentals
chapter:
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Super Resolution Problem Statement
Blind image super-resolution (BISR), which aims to reconstruct a high-resolution (HR) image from its low-resolution (LR) counterpart without knowing the degradation kernel and noise, is a very challenging computer vision problem. The degradation process from an HR image to an LR image can be expressed as:
$$
\mathbf{Y}=(\mathbf{K} \circledast \mathbf{X}) \downarrow_s+\mathbf{n}
$$
where $\mathbf{X}$ is the HR image, $\mathbf{Y}$ is its observed LR counterpart, $\mathbf{K}$ is the blur kernel, $\circledast$ is the $2 \mathrm{D}$ convolution operator, $\downarrow_s$ is the downsampling operator with scaling factor $s$, and $\mathbf{n}$ is the additive white Gaussian noise.







