---
title: Variational Autoencoder Introduction
date: 01-06-2023
time: 17:39
author: Luca Trautmann
tags: ["VAE","ML"]
series: "Variational Autoencoder"
chapter: 0
---

# Variational Autoencoder Introduction
## General Introduction Variational Autoencoder, Intuitive Example
Suppose now, instead of placing every item of clothing at a single point in the wardrobe, you decide to allocate a general area where the item is more likely to be found. You reason that this more relaxed approach to item location will help to solve the current issue around local discontinuities in the wardrobe. Also, in order to ensure you do not become too careless with the new placement system, you agree with Brian that you will try to place the center of each item’s area as close to the middle of the wardrobe as possible and that deviation of the item from the center should be as close to one meter as possible (not smaller and not larger). The further you stray from this rule, the more you have to pay Brian as your stylist. After several months of operating with these two simple changes, you step back and admire the new wardrobe layout, alongside some examples of new clothing items that Brian has generated. Much better! There is plenty of diversity in the generated items, and this time there are no examples of poor-quality garments. It seems the two changes have made all the difference!

## Loss Function for Variational Autoencoder
$$
\text{Loss} = \text{Reconstruction Loss} + \beta \cdot \text{KL Divergence}
$$








related: [[Kullback-Leibler (KL) divergence]]  [[Variational Inference]]

# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```