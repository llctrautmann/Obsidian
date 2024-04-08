---
title: Autoencoder
date: 18-05-2023
time: 15:07
author: Luca Trautmann
tags: ["ML"]
series: "Machine Learning Models"
chapter: 1
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```


# Autoencoder
An Autoencoder is a type of neural network consisting of two networks, the encoder and decoder networks. The encoder takes an input and reduces it into a lower dimensional latent space, while the decoder takes the latent space and attempts to reconstruct the original image. 



