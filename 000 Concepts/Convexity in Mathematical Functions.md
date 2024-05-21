---
title: Convexity in Mathematical Functions
date: 05-06-2023
time: 10:14
author: Luca Trautmann
tags: ["Mathematics"]
series: "Mathematics & Statistics"
chapter: 4
---

# Convexity in Mathematical Functions
<mark style="background: #FF5582A6;">A function is convex if we can draw a straight line between any two points on the function, and this line always lies above the function. Similarly, a function is concave if a straight line between any two points always lies below the function.</mark> By definition, convex (concave) functions have at most one minimum (maximum).

A region of $\mathbb{R}^D$ is convex if we can draw a straight line between any two points on the boundary of the region without intersecting the boundary in another place. Gradient descent guarantees to find the global minimum of any function that is both convex and defined on a convex region.

### Example Convex Function
```chart
type: line
labels: [-3. , -2.34, -1.67, -1. , -0.34, 0.34, 1. , 1.67, 2.34, 3. ]
series:
  - title: Y
    data: [9. , 5.44444444, 2.77777778, 1. , 0.11111111, 0.11111111, 1. , 2.77777778, 5.44444444, 9. ]
tension: 0.2
width: 80%
labelColors: false
fill: false
beginAtZero: false
bestFit: false
bestFitTitle: undefined
bestFitNumber: 0
```

### Example Concave Function
```chart
type: line
labels: [-3. , -2.34, -1.67, -1. , -0.34, 0.34, 1. , 1.67, 2.34, 3. ]
series:
  - title: Y
    data: [-9. , -5.44444444, -2.77777778, -1. , -0.11111111, -0.11111111, -1. , -2.77777778, -5.44444444, -9. ]
tension: 0.2
width: 80%
labelColors: false
fill: false
beginAtZero: false
bestFit: false
bestFitTitle: undefined
bestFitNumber: 0
```





# Chapters
```dataview
TABLE chapter as Chapter
FROM "Concepts"
WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
SORT chapter asc
```