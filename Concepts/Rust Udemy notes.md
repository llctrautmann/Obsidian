---
title: Rust Udemy notes
date: 06-01-2024
time: 13:59
author: Luca Trautmann
tags: 
series: Rust
chapter:
---

> [!Chapters]-
> ```dataview
> TABLE chapter as Chapter
> FROM "concepts"
> WHERE (series = this.series AND chapter = this.chapter + 1) OR (series = this.series AND chapter = this.chapter - 1)
> SORT chapter asc
> ```

# Rust Udemy notes

structs In rust are a bit like data classes in python. They allow me to collect data and use the data related context.
It is not possible to output a struct with a print statement but It requires the flag `#[derive(Debug)]`. 


## Enums
— In Python, the equivalent of a Rust enum would typically be a **class hierarchy using inheritance**.

Enum: **Class inheritance** in Python

**Create** Enum ?

```Rust
#[derive(Debug)] // use for debug -> println!({:?});  
enum Color {  
    Red,  
    Green,  
    Blue  
}  

  
let red = Color::Red;  
println!("{red:?}"); // Red
```


**add function** by `impl`

```Rust
impl Color {  
    fn describe(&self) -> &str {  
        match self {  
            Color::Red => "It's red",  
            Color::Green => "It's green",  
            Color::Blue => "It's blue",  
        }  
    }  
}  

  
println!("{}", red.describe()); // It's red
```

**Why we need Enum ?**

- Improved Readability
- Compile-Time Type Safety : strongly typed, It helps prevent runtime errors.
- Pattern Matching : in pattern matching (`match` expressions) allows you to easily handle different cases.

**What’s the difference between struct and enum ?**

- <mark style="background: #FF5582A6;">struct : grouping related data fields.</mark>
- <mark style="background: #BBFABBA6;">enum : representing a value that can be one of several known possibilities.</mark>

```Rust
struct point {  
  x: i32,  
  y: i32,  
  z: i32  
}  
  
enum color {  
  Red,  
  Green,  
  Blue  
}
```