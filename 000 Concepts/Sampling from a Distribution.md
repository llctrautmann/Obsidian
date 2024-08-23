---
title: Sampling from a Distribution
date:
  - 04-06-2023
time: 12:16
author: Luca Trautmann
tags: 
series: Probability Theory
chapter: 14
modified: 2024-08-23
---

# Sampling from a Distribution
Sampling from a distribution means to draw a number of numbers randomly given the probabilities described by a PDF or PMF (see: [[Density Functions]])

Reference: StatQuest - https://www.youtube.com/watch?v=XLCWeSVzHUU









# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```