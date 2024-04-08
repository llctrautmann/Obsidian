---
modified: 2024-02-08
---
# Notes Creation History 
## Notes Today
```dataview
TABLE series as Series, file.ctime as Time
FROM "Concepts"
WHERE file.cday = date(today)
SORT file.ctime DESC
```

## Notes Yesterday
```dataview
TABLE series as Series, file.ctime as Time
FROM "Concepts" OR "Articles"
WHERE file.cday = date(yesterday)
SORT file.ctime DESC
```

## Notes Last Week
```dataview
TABLE series as Series, file.ctime as Time
FROM "Concepts" OR "Articles"
WHERE file.cday > date(today) - dur(7 day)
SORT file.ctime DESC
```

## Notes Last Month
```dataview
TABLE series as Series, file.ctime as Time
FROM "Concepts"
WHERE file.cday > date(today) - dur(31 day)
SORT file.ctime DESC
```

## Notes Last Year
```dataview
TABLE series as Series, file.ctime as Time
FROM "Concepts"
WHERE file.cday > date(today) - dur(365 day)
SORT file.ctime DESC
```
