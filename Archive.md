---
title: Series Bibliography
date: 20-05-2023
time: 14:28
author: Luca Trautmann
tags: []
modified: 2024-04-02
---

> As the old saying goes, if you want something, you find ways, otherwise, you try to find excuses...

> Believe in yourself and proof them wrong!

# Books
## M4ML
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "M4ML"
SORT chapter asc
```

## PT
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "PT"
SORT chapter asc
```

## Probabilistic Machine Learning
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "PML"
SORT chapter asc
```

## Generative Deep Learning
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "GDL"
SORT chapter asc
```

## Student's guide to Bayesian Statistics
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "SGBS"
SORT chapter asc
```

# Themes

## Linear Algebra
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts" OR "Articles"
WHERE series = "Linear Algebra"
SORT chapter asc
```

## Probability Theory
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts" OR "Articles"
WHERE series = "Probability Theory"
SORT chapter asc
```

## Information Theory
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "Information Theory"
SORT chapter asc
```

## Machine Learning Fundamentals
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "Machine Learning Fundamentals"
SORT chapter asc
```

## Machine Learning Models
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "Machine Learning Models"
SORT chapter asc
```

## Mathematics & Statistics
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "Mathematics & Statistics"
SORT chapter asc
```

## Variational Autoencoder
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "Variational Autoencoder" OR series = ["Variational Autoencoder","Machine Learning Fundamentals"]
SORT chapter asc
```

## Audio-processing
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "Audio-processing"
SORT chapter asc
```

# Langs

## Python / PyTorch
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "PyTorch" OR series = "Python"
SORT chapter asc
```

## Rust
```dataview
TABLE series as Series, chapter as Chapter, keywords as Keywords
FROM "Concepts"
WHERE series = "Rust"
SORT chapter asc
```

## SQL
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
WHERE series = "SQL"
SORT chapter asc
```



# Everything
```dataview
TABLE series as Series, chapter as Chapter
FROM "Concepts"
SORT chapter asc
```
