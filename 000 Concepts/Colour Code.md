---
title: Colour Code
date: 14-08-2023
time: 16:39
author: Luca Trautmann
tags: []
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

# Colour Code

<mark style="background: #FFF3A3A6;">Yellow</mark> = Important Text passages

<mark style="background: #ADCCFFA6;">Blue</mark> = Further Research anchors

<mark style="background: #BBFABBA6;">green</mark> = goals and conclusions

<mark style="background: #FFB8EBA6;">pink</mark> = marker for GPT task











