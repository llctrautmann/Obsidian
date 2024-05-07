---
modified: 2024-05-07
---
```dataview
TABLE modified as "Last Change"
FROM "Concepts" OR "Articles"
WHERE file.cday > date(today) - dur(7 day)
SORT file.ctime DESC
```
