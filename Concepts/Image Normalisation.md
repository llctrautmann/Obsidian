---
title: Image Normalisation
date: 17-12-2023
time: 17:42
author: Luca Trautmann
tags:
  - PyTorch
series: Coding
chapter:
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Image Normalisation
When an image is transformed into a PyTorch tensor, the pixel values are scaled between 0.0 and 1.0. In PyTorch, this transformation can be done using **torchvision.transforms.ToTensor()**. It converts the PIL image with a pixel range of [0, 255] to a PyTorch FloatTensor of shape (C, H, W) with a range [0.0, 1.0].










