---
title: VAE Algorithm
date: 13-06-2023
time: 09:25
author: Luca Trautmann
tags: ["ML","VAE"]
series: "Variational Autoencoder"
chapter: 8
---

# VAE Algorithm
The formula for the ELBO in the context of the Variational Autoencoder is hence given by the following:
$$
\operatorname{ELBO}[\boldsymbol{\theta}, \boldsymbol{\phi}]=\int q(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\theta}) \log [\operatorname{Pr}(\mathbf{x} \mid \mathbf{z}, \boldsymbol{\phi})] d \mathbf{z}-\mathrm{D}_{K L}[q(\mathbf{z} \mid \mathbf{x}, \boldsymbol{\theta}) \| \operatorname{Pr}(\mathbf{z})] \text {, }
$$

## VAE Overview
![[VAE_Overview.png]]







# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```
