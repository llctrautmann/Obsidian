---
title: SQL Overview
date: 04-07-2023
time: 16:01
author: Luca Trautmann
tags: []
series: SQL
chapter: 1
---

# SQL Database Overview
## Advantages of Databases:
- Data Integrity (everything stays the same)
- Data size 
- Combining datasets
- Automation for re-use 
- Website support and application support

## From Spreadsheets to Databases
- Spreadsheet Tabs = Tables
- Columns = Columns
- Rows = Rows

## PostgreSQL
- great for learning
- SQL can be applied to all different types of databases










# Chapters
```dataview
TABLE chapter as Chapter
FROM "concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```