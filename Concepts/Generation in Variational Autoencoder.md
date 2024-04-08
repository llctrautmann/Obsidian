---
title: Generation in Variational Autoencoder
date: 04-06-2023
time: 11:41
author: Luca Trautmann
tags: ["ML","VAE"]
series: "Variational Autoencoder"
chapter: 5
---

# Generation in Variational Autoencoder
- The main purpose of any generative model is to create new objects
- Within the VAE framework this occurs by sampling a data point from the distribution (see: [[Sampling from a Distribution]] for more details on how this is done for a simple distribution such as the normal distribution)

## Ancestral Sampling
- Ancestral Sampling is the main technique used for this kind of sampling
- There are three stages to ancestral sampling: (1) draw a sample from the prior distribution (2) A new sample is then drawn from the likelihood






# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```