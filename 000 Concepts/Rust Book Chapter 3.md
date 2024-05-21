---
title: Rust Book Chapter 3
date: 12-01-2024
time: 14:38
author: Luca Trautmann
tags: []
series: Rust
chapter: 3
keywords: Rust, Variables, Mutability, Constants, Shadowing, Data Types, Basic Operations, Integers, Floating Point Numbers, Bools, Character Type, Tuples, Array, Functions, Parameters, Statements, Expressions, Return Values, Control Flow, if Expressions, Repetitions, Loops, Loop Labels, Conditional Loops
---
# Rust Book Chapter 3
## Variables and Mutability
Rust variables are by default __not mutable__. 

```rust
let x1 = 5;

// To make a variable mutable use the keyword mut

let mut x2 = 6; // this variable is now mutable
```

The Rust compiler guarantees that when you state that a value won’t change, it really won’t change, so you don’t have to keep track of it yourself.


## Constants
```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```
`Constants ` are like immutable variables but with some differences. These are: 
1. You cannot use `mut` with constants
2. requires annotation of the datatype 

Rust’s naming convention for constants is to use all uppercase with underscores between words. As per usual, constants are valid for the then entire time the program runs, within the scope in which they were declared. 

> use constants for permanent hyperparameters in machine learning training loops

## Shadowing
Declaring a variable with the same name as a previous variable is called shadowing. The compiler will only see the second variable. In effect, the second variable overshadows the first, taking any uses of the variable name to itself until either it itself is shadowed or the scope ends. 

```rust
fn main() {
    let x = 5;

    let x = x + 1;

    {
        let x = x * 2;
        // in the inner scope the variable is now 12
        println!("The value of x in the inner scope is: {x}");
    }
	// The inner scope has ended here and the value is now 6
    println!("The value of x is: {x}");
}

Excerpt From
The Rust Programming Language
Steve Klabnik
This material may be protected by copyright.
```

If shadowing is used the value is still immutable and hence there is a difference to a mutable value created with `let mut`. 

Shadowing allows for neat naming of variables in programmes. For example: 
```rust
let spaces = "   ";
let spaces = spaces.len(); // allows the variable to be called the same
```

Also possible would be: 

```rust
let space = "    ";

{
let space = space.len();
// add follow up code in the scope
}

println!("{}", space);
// This will print out the string of spaces
```

## Data Types
### Basic Operations 
```rust
“fn main() {
    // addition
    let sum = 5 + 10;

    // subtraction
    let difference = 95.5 - 4.3;

    // multiplication
    let product = 4 * 30;

    // division
    let quotient = 56.7 / 32.2;
    let truncated = -5 / 3; // Results in -1

    // remainder
    let remainder = 43 % 5;
}
```


### Integers
Each signed variant can store numbers from $–(2^{n – 1})$ to $2^{n – 1} – 1$ inclusive, where n is the number of bits that variant uses. So an i8 can store numbers from $–(2^7)$ to $2^7 – 1$, which equals $–128$ to $127$. Unsigned variants can store numbers from $0$ to $2^{n – 1}$, so a u8 can store numbers from $0$ to $2^8 – 1$, equaling 0 to $255$.

Additionally, the isize and usize types depend on the architecture of the computer your program is running on, which is denoted in the table as “arch”: 64 bits if you’re on a 64-bit architecture and 32 bits if you’re on a 32-bit architecture.

### Floating Point Numbers
 There are f32 and f64 floats.

### Bools
```rust
fn main() {
    let t = true;

    let f: bool = false; // with explicit type annotation
}
```

### Character Type
The most primitive alphabet type in Rust is the `char` type. 

> Rust’s char type is four bytes in size and represents a Unicode scalar value, which means it can represent a lot more than just ASCII.

However, a “character” isn’t really a concept in Unicode, so your human intuition for what a “character” is may not match up with what a char is in Rust.

### Tuples
- immutable but can contain different datatypes

```rust
fn main() {
    let tup = (500, 6.4, 1);

    let (x, y, z) = tup; // tuple unpacking

    println!("The value of y is: {y}");
	}
```

### Array

- Unlike a tuple, every element of an array must have the same type. Unlike arrays in some other languages, arrays in Rust have a fixed length.
- example: `let a = [1,2,3,4,5]`
- There is also a vector type which grants more flexibility in the length (see [[Rust Book Chapter 8]] for more detail)

```rust
// neat trick for arrays
let a = [3; 5]; // result [3,3,3,3,3]
```

Accessing Arrays works just like in Python: 
```rust
fn main() {
    let a = [1, 2, 3, 4, 5];

    let first = a[0];
    let second = a[1];
}
```

> Attempting to index an invalid Element will be caught at runtime and throws and error. Rust protects against dangling pointers and accessing the wrong type of memory.

## Functions
Convention dictates that snake case is used to name functions. The main key word is `fn` :

```rust
fn main() {
    println!("Hello, world!");

    another_function();
}

fn another_function() {
    println!("Another function.");
}
```

### Parameters
Parameters are special values that are part of a functions signature. There is not much of a difference to python. Arguments __must__ be type declared to make things bug-proof. 

```rust
fn main() {
    print_labeled_measurement(5, 'h');
}

fn print_labeled_measurement(value: i32, unit_label: char) {
    println!("The measurement is: {value}{unit_label}");
}
```

### Statements and Expressions
- Statements are instructions that do not return a value
- Expressions evaluate to a resultant value 

```rust
fn main() {
	let y = 6; 
}
// this entire expression is a statement

let = 5; // this is also a statement as the let command does not return a value
let x = let y = 5 // does not work as let does not return anything and hence nothing can be bound to x.
```

```rust
fn main() {
  ❶ let y = {❷ // 1 = statement | 2 = expression, 3 = expression
        let x = 3;
      ❸ x + 1 // expressions do not get a semi-colon 
    };

    println!("The value of y is: {y}");
}
```
If you add a semicolon to the end of an expression, you turn it into a statement, and it will then not return a value. Keep this in mind as you explore function return values and expressions next.

### Functions with Return Values
Functions can return values. In such cases, the function needs to include the returned data type

```rust
fn five() -> i32 {
	5 // note: no semicolon hence expression which is returned
}
```

## Control Flow
### if Expressions
```rust
fn main() {
    let number = 3;

	if number % 4 == 0 {
        println!("number is divisible by 4");
    } else if number % 3 == 0 {
        println!("number is divisible by 3");
    } else if number % 2 == 0 {
        println!("number is divisible by 2");
    } else {
        println!("number is not divisible by 4, 3, or 2");
    }
}
```

> note: unlike python non-bools will not be auto-coverted into bools, but requires explicit statements of boolean conditions in the conditional. 

If and else statements need to be of the same datatype. Mixed types won’t work because variables must have a single type, and Rust needs to know at compile time what type the number variable is, __definitively__.


### Repetitions and Loops and returning from loop
There are three types of loops: `loop`, `while`, and `for`.

`loop` is the simples type and just repeats the code indefinitely or until a `break` statement is triggered. `continue` also exists in rust and behaves just like in python. 

```rust
fn main() {
    let mut counter = 0;

    let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2; // the value is returned out of the loop
        }
    };

    println!("The result is {result}");
}
```

### Loop Labels
loop labels allow for targeted break statements. If loops are nested we can specify which loop should be exited or continued from a match condition. 

```rust
fn main() {
    let mut count = 0;
    'counting_up: loop { // 'counting_up is the label of the loop
        println!("count = {count}");
        let mut remaining = 10;
        .
        .
        .
	    if count == 2 {
		    break 'counting_up;
	    }
```

### Conditional Loops with while and for
The behaviour is the same as in other programming languages. 

```rust
fn main() { //while loop
    let mut number = 3;

    while number != 0 {
        println!("{number}!");

        number -= 1;
    }

    println!("LIFTOFF!!!");
}
```

```rust
fn main() {
    let a = [10, 20, 30, 40, 50];

    for element in a {
        println!("the value is: {element}");
    }
}

// An alternative way to multiply integers in an array would be to
fn grow(array: Vec<i32>) -> i32 {
    array.iter().product() 
} 
```
