---
title: Git Config
date: 11-08-2023
time: 20:45
author: Luca Trautmann
tags: 
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

# GIt Config
## Change commit template
```bash
git config commit.template /absolute/path/to/file

or

git config commit.template relative-path-from-repository-root
```











