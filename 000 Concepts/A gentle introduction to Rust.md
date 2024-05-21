---
title: A gentle introduction to Rust
date: 07-12-2023
time: 09:56
author: Luca Trautmann
tags: 
series: Rust
chapter: 0
---


# A gentle introduction to Rust
## Principles
The unifying principles behind Rust are:

- strictly enforcing _safe borrowing_ of data
- functions, methods and closures to operate on data
- tuples, structs and enums to aggregate data
- pattern matching to select and destructure data
- traits to define _behaviour_ on data

## Basics
Rust is a curly-braces language with semicolons, C++-style comments and a `main` function - so far, so familiar. The exclamation mark  in `println!` indicates that this is a _macro_ call.

### Variables
```rust
// let1.rs 
fn main() {
	let answer = 42;
	println!("Hello {}", answer);
	}
```

### Macros
`println!` is a macro not a function. Another very useful macro is `assert_eq!`, which checks for equality between two things in rust.

```rust
// let2.rs 
fn main() {
	let answer = 42;
	assert_eq!(answer,42);
}
```

### looping and ifing
Anything interesting can be done more than once:

```rust
// for1.rs
fn main() {
	for i in 0..5 {
		println!("Hello {}", i);
		}
	}
```
The range is not inclusive, so i goes from 0 to 4. This is convenient in a language which indexes things like arrays from 0.

Interesting things need also be done conditionally:

```rust
//src.rs
fn main() {
	for i in 0..5 {
		if i % 2 == 0 {
			println!("even {}", i);
			} else {
			println!("odd {}", i);}
		}
	}
```

### Adding
```rust
fn main() {
	let mut sum = 0;
	for i in 0..100 {
		sum += i
		}
	println!("Total sum = {}", sum)
}
```

> [!Note]-
>  This can be puzzling when coming from other languages, where variables can be re-written by default. What makes something a 'variable' is that it gets assigned a computed value at run-time - it is not a _constant_. It is also how the word is used in mathematics, like when we say 'let n be the largest number in set S'.

There is a reason for declaring variables to be _read-only_ by default. In a larger program, it gets hard to track where writes are taking place. So Rust makes things like mutability ('write-ability') explicit. There's a lot of cleverness in the language, but it tries not to hide anything.

## Function Types are Explicit
This means for each function I need to add exactly what datatype the input and the output are. 

```rust
// fun1.rs
fn sqr(x: f64) -> f64 {
	return x * x;
	}
	
fn main() {
	let res = sqr(2.0);
	println!("square is {}", res);
	}
```

More generally the idiomatic form is:
```rust
fn example_function(input: InputType) -> OutputType {
    // function body
}
```

In addition, return statements are not required except for early exiting a function scope. The last line of a function - if used without `return` will complain if a semi-colon is added. <mark style="background: #FFB8EBA6;">Passing by reference is important when we have a large object and don't wish to copy it. So it makes things pretty memory efficient.</mark>  

## Learning Where to find the Ropes
To get a full offline documentation use:
```bash
rustup doc --std
```

To import something use: 

```rust
use crate::type::thing 
```

## Arrays and Slices
All statically-typed languages have _arrays_, which are values packed nose to tail in memory. Arrays are _indexed_ from zero: 

```rust 
//arrayn1.rs

fn main() {
	let arr = [10,20,30,40]
	let first = arr[0]
	println!("first {}", first)

	for i in 0..4 {
	println("[{}] = {}", i, arr)
	}
	println!("length {}", arr.len())
}
```

Learning a new language often involves _unlearning_ mental habits from languages you already know; if you are a Pythonista, then those brackets say `List`. We will come to the Rust equivalent of `List` soon, <mark style="background: #FFB8EBA6;">but arrays are not the droids you're looking for; they are _fixed in size_. They can be _mutable_ (if we ask nicely) but you cannot add new elements.</mark>

Arrays are not used that often in Rust, because the type of an array includes its size. The type of the array in the example is `[i32; 4]`; the type of `[10, 20]` would be `[i32; 2]` and so forth: they have _different types_. So they are bastards to pass around as function arguments.

What _are_ used often are _slices_. You can think of these as _views_ into an underlying array of values. They otherwise behave very much like an array, and _know their size_, unlike those dangerous animals C pointers.

```rust
// array2.rs 
// read as: slice of i32
fn sum(values: &[i32]) -> i32 {
	let mut res = 0;
	for i in 0..values.len() {
		res += values[i]
		}
	res 
	}

fn main() {
	let arr = [10,20,30,40]; // look at that & 
	let res = sum(&arr);
	println!("sum {}", res);
	}
```

Rust slices keep track of their size (and will panic if you try to access outside that size) and you have to explicitly say that you want to pass an array as a slice using the `&` operator.

__A C programmer pronounces `&` as 'address of'; a Rust programmer pronounces it 'borrow'.__ This is going to be the key word when learning Rust. Borrowing is the name given to a common pattern in programming; whenever you pass something by reference (as nearly always happens in dynamic languages) or pass a pointer in C. Anything borrowed remains owned by the original owner.

## Slicing and Dicing