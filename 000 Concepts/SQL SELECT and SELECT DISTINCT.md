---
title: SQL SELECT and SELECT DISTINCT
date: 05-07-2023
time: 14:02
author: Luca Trautmann
tags: []
series: SQL
chapter: 2
---

# SQL SELECT and SELECT DISTINCT
## SELECT
- selects the columns that are being specified in the query 
```sql
SELECT name, height FROM register
```

## SELECT DISTINCT
- only selects the unique values from the query
```sql
SELECT DISTINCT column FROM registery
```










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```