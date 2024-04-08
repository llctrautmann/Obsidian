---
title: Uncertainty Introduction
date: 26-08-2023
time: 17:19
author: Luca Trautmann
tags: ["Uncertainty"]
series: 
chapter: 
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Uncertainty Introduction
- Probability is used to quantify and analyse uncertainty in a systematic manner. In doing so, we reject the vacuous distinction between risk and uncertainty.










