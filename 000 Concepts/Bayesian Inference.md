---
title: Bayesian Inference
date: 01-06-2023
time: 16:27
author: Luca Trautmann
tags: []
series: ["Variational Autoencoder","Machine Learning Fundamentals"]
chapter: 3
---

# Bayesian Inference
From a bayesian perspective, the maximum likelihood criterion can be improved with either <mark style="background: #FFB8EBA6;">maximum a posteriori (MAP) estimation</mark> or a full approximation of the posterior distribution over the parameters.










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = "Variational Autoencoder" AND chapter = this.chapter + 1) OR (series = "Variational Autoencoder" AND chapter = this.chapter - 1)
SORT chapter asc
```