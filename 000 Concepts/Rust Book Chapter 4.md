---
title: Rust Book Chapter 4
date: 15-01-2024
time: 09:19
author: Luca Trautmann
tags: 
series: Rust
chapter: 4
keywords: Rust, Ownership, Borrowing, Stack, Heap, String, Memory Allocation, Move, Clone, Copy, References, Mutable References, Slice, UTF-8, Memory Safety, Compile Time, Variable Scope, Ownership Rules
---
s# Rust Book Chapter 4
## Understanding Ownership

Borrowing and Ownership are core concepts in rust that set the Rust programming language apart from other languages. It enables Rust to make memory safety guarantees without needing a garbage collector.

## What is Ownership?
Ownership are the core rules in Rust that dictate how memory is used and allocated by objects within the scope of a program. 

> “Rust uses a third approach: memory is managed through a system of ownership with a set of rules that the compiler checks. If any of the rules are violated, the program won’t compile. None of the features of ownership will slow down your program while it’s running.”
> 
> Excerpt From
> The Rust Programming Language
> Steve Klabnik
> This material may be protected by copyright.

## The Stack and the Heap
In systems programming languages like Rust, it is important to consider whether a value is located on the __stack__ or on the __heap__. Both the stack and the heap are parts of memory available to your code to use at runtime, but they are structured in different ways. 

__The stack__: stores values in the order it gets them and removes the values in the opposite order. This is referred to as last in, first out. Adding data is called pushing onto the stack, and removing data is called popping off the stack. All data stored on the stack must have a known, fixed size. Data with an unknown size at compile time or a size that might change must be stored on the heap instead.

__The heap__ is less organised: when you put data on the heap, you request a certain amount of space. The memory allocator finds an empty spot in the heap that is big enough, marks it as being in use, and returns a pointer, which is the address of that location. This process is called allocating on the heap and is sometimes abbreviated as just allocating. The pointer can be stored on the stack as it is fixed size, but it is necessary to follow the pointer to retrieve the stored data. 

__Pushing to the stack is faster than allocating on the heap because the allocator never has to search for a place to store new data__; that location is always at the top of the stack. Comparatively, allocating space on the heap requires more work because the allocator must first find a big enough space to hold the data and then perform bookkeeping to prepare for the next allocation.

## Ownership Rules
There are three fundamental rules of ownership: 
1. Each value in Rust has an owner.
2. There can only be one owner at a time.
3. When the owner goes out of scope, the value will be dropped.

## Variable Scope
Variables are valid from the point at which they are declared until the end of the current scope. 

```rust
{                      // s is not valid here, since it's not yet declared
    let s = "hello";   // s is valid from this point forward
	.
	.
	.
    // do stuff with s
}                      // this scope is now over, and s is no longer valid”

```

## The string type as an example of a data type stored on the heap
String `literals` are easy, hard coded, and reside on the stack. They do not pose a major challenge but they are also immutable and hence only of limited use in programmes (think I/O for a example that require a more advanced data structure). 

`Strings` are managed on the heap and can perform much more advanced tasks. To create a string we can use the `String::from` method. 

```rust
let s = String::from("Hello");
```

This type of string can also be mutable. 

```rust
let mut s = String::from("Hello");

// this then allows for other methods to be applied to the sting like pushing and popping

s.push_str(", world!"); // Adds , world! to hello

println!("{}", s); // Prints hello world!
```

### Memory and Allocation for `strings` and `literals`
__The immutable nature of the `literal` allows for it to be written directly into the executable, at compile time__. This is fast and efficient but also highlights why they need to be immutable. It would be impossible to allocate free memory and reserve space in the binary for an unknown length amount of input data.

With the String type, in order to support a mutable, growable piece of text, we need to allocate an amount of memory on the heap, unknown at compile time, to hold the contents. This means: __The memory must be requested from the memory allocator at runtime.__

```
Remember: 
Literal -> @ compile time;
String -> @ runtime;
```

After the memory has been used the memory needs to be returned. Traditionally, this has been done manually (think C) or with a garbage collector (think GO) and is a frequent source of errors. Rust handles this automatically, __by returning free memory after a variable goes out of scope__. Under the hood Rust calls a special function `drop` to free the memory. 

> Note: 
	In C++, this pattern of deallocating resources at the end of an item’s lifetime is sometimes called Resource Acquisition Is Initialization (RAII). The drop function in Rust will be familiar to you if you’ve used RAII patterns. See also: https://www.youtube.com/watch?v=pTMvh6VzDls for a good explanation of the memory management in rust.

## Variables and Data Interacting with Move
Multiple variables can interact with the same data in different ways in Rust. 

```rust
// within a scope a new variable can be assigned to an existing variable

let x = 5;

let y = x; // makes a copy of x and binds it to y 
```

This works because integers are on the stack and simple fixed size datatypes. But for more complex (heap related) datatypes, the situation is different. Lets see the changes in code. 

```rust
let s1 = String::from("Hello");

let s2 = s1; // looks similar but does something different under the hood 
```

When we assign s1 to s2, the String data is copied, meaning we copy the pointer, the length, and the capacity that are on the stack. We do not copy the data on the heap that the pointer refers to.

One issue that requires ownership to be always connected to a singular instance are __double free error__. As the name suggests a double free error, effectively means that `drop` is called on the same memory twice. This could then lead to corrupted files and security vulnerabilities. Hence Rust needs a solution for this issue. 

Rust does so by considering only `s2` to be valid and not `s1`. Using s1 after it has been invalidated will lead to a compile error. 

## Move in Rust
Copying only the pointer, length and capacity and not the heap data is in other languages referred to as a shallow copy. Copying also the data in the heap is usually called a deep copy. In rust, due to the first variable being invalidated, the operation is called a __move__. 

```rust
let s1 = String::from("Hello");

let s2 = s1; // looks similar but does something under the hood 

// Here s1 would be moved into s2
```

## Variable and Data Interacting with Clone
If we do want to deeply copy the heap data of the String, not just the stack data, we can use a common method called clone.

```rust
let s1 = String::from("hello");
let s2 = s1.clone();

println!("s1 = {s1}, s2 = {s2}");
```

## Stack-only Data: Copy
__If the data resides completely on the stack any copy that is made can be done without `.clone`. This is so, because copies on the stack are efficient and inexpensive, if they only happen exclusively on the stack and do not require any involvement of the heap.__ There are some dynamics with `copy traits` that will be discussed in [[Rust Book Chapter 10]]. Using the `copy` trait will make variables usable after they have been assigned to another variable, as they are trivially copied and not invalidated.

The types to which copy can be applied are: 
- All the integer types, such as u32.
- The Boolean type, bool, with values true and false.
- All the floating-point types, such as f64.
- The character type, char.
- Tuples, if they only contain types that also implement Copy. For example, (i32, i32) implements Copy, but (i32, String) does not.

## Ownership and Functions
The mechanics of passing a value to a function are similar to those when assigning a value to a variable. Passing a variable to a function will move or copy, just as assignment does.

```rust
fn main() {
    let s = String::from("hello");  // s comes into scope

    takes_ownership(s);             // s's value moves into the function...
                                    // ... and so is no longer valid here

    let x = 5;                      // x comes into scope

    makes_copy(x);                  // x would move into the function,”
								    // but i32 is Copy, so it's okay to still
									// use x afterward

	} // Here, x goes out of scope, then s. However, because s's value was moved,
	  // nothing special happens.

	fn takes_ownership(some_string: String) { // some_string comes into scope
	    println!("{some_string}");
	} // Here, some_string goes out of scope and `drop` is called. The backing
	  // memory is freed.

	fn makes_copy(some_integer: i32) { // some_integer comes into scope
	    println!("{some_integer}");
	} // Here, some_integer goes out of scope. Nothing special happens.
```

(There is a cargo project "Ownership" that plays with these code examples). 

## Return Value and Scope
Returning values can also transfer ownership. 

```rust
fn gives_ownership() -> String {
	let some_string = String::from("yours"); // some_string comes into scope
	some_string // returns some_string
}

fn takes_and_gives_back(a_string: String) -> String {
	a_string
}

fn main() {
	let s1 = gives_ownership();	// moves the scope into main 

	let s2 = String::from("hello");

	let s3 = takes_and_gives_back(s2); 
} 
// Here, s3 goes out of scope and is dropped. 
//s2 was moved, so nothing happens. s1 goes out of scope and is dropped.
```

__The ownership of a variable follows the same pattern every time: assigning a value to another variable moves it.__ When a variable that includes data on the heap goes out of scope, the value will be cleaned up by `drop` unless ownership of the data has been moved to another variable.

## References, Mutable References and Borrowing
References are pointers to the value in heap memory that do not contain any other information. The ownership of the data remains with the original variable. Unlike a C++ pointer, a reference is guaranteed to point to a valid value of a particular type for the life of that reference, otherwise the compiler throws an error. 

```rust
fn calculate_length(s: &String) -> usize {
	s.len()
}
 
fn main() {
	let s1 = String::from("Hello");
	let len = calculate_length(&s1); // s1 is being borrowed 
}
```

mutable references also exist and, allow a function to change a mutable object. For example:

```rust
fn add_word(s1: &mut string) {
	s1.push_str(", World!");
}

fn main() {
	let mut s1 = String::from("Hello");
	add_word(s1);

	println!("{}", s1);
}
```



Because the variable is referenced and not owned it is not destroyed with `drop` at the end of the scope. When functions have references as parameters instead of the actual values, we won’t need to return the values in order to give back ownership, because we never had ownership. This entire process is called __borrowing__.

### The Rules of References
1. At any given time, you can have either one mutable reference or any number of immutable references.
2. References must always be valid.


## The Slice Type
Slices allow for referencing of contiguous sequences of elements in a collection rather than the whole collection. __Slices are references and therefore do not have ownership__.

### String Slices
A string slice is a reference to a part of a string and looks as follows: 

```rust
fn main() {
	let s = String::from("Hello");

	let hello = &s[0..5]; 
	let world = &s[6..11];
}
```

Internally, the slice data structure stores the starting position and the length of the slice, which corresponds to _ending_index_ minus _starting_index_. So, in the case of `let world = &s[6..11];`, world would be a slice that contains a pointer to the byte at index 6 of s with a length value of 5.

> Note:
> String slice range indices must occur at valid UTF-8 character boundaries. If you attempt to create a string slice in the middle of a multibyte character, your program will exit with an error. [[Rust and UTF-8 characters]] for more information. 


# Summary
The concepts of ownership, borrowing, and slices ensure memory safety in Rust programs at compile time. The Rust language gives you control over your memory usage in the same way as other systems’ programming languages, but having the owner of data automatically clean up that data when the owner goes out of scope means you don’t have to write and debug extra code to get this control.
Ownership affects how lots of other parts of Rust work, so we’ll talk about these concepts further throughout the rest of the book. Let’s move on to Chapter 5 and look at grouping pieces of data together in a struct.
