---
title: Rust Book Chapter 5
date: 16-01-2024
time: 18:02
author: Luca Trautmann
tags: 
series: Rust
chapter: 5
keywords:
---
# Using Structs to Structure Related Data
A struct, or structure, is a custom data type that lets you package together and name multiple related values that make up a meaningful group. 

## Defining and Instantiating Structs
Similarly to tuples structs hold multiple related values. Unlike with tuples, in a struct you’ll name each piece of data so it’s clear what the values mean. Adding these names means that structs are more flexible than tuples: you don’t have to rely on the order of the data to specify or access the values of an instance.

```rust
fn main() {
	struct User { 
    active: bool, // These are called fields 
    username: String,
    email: String,
    sign_in_count: u64,
	}
}
```

To use a `struct` we create an instance of it, by specifying concrete values for each field. __We create an instance by stating the name of the struct and then add curly brackets containing `key:value` pairs__. 

```rust
fn main() {
	let user1 = User {
	active: true,
	username: String::from("0xFahrenheit"),
	email: String::from("guy_montag@posteo.net"}
	sign_in_count: 1,
}

// To retrive a value we use dot notation

user1.email = String::from("lucatrautmann@protonmail.com")

println!("{}",user1.username) // This should return 0xFahrenheit 
```

## Creating Instance from Other Instances with Struct Update Syntax
If necessary it is possible to update a `struct` and maintain most values of an existing struct. This is done with __Struct update Syntax__. The syntax is as follows: 

```rust
fn main() { // This is syntax without Struct update Syntax
	let user2 = User {
		active = user1.active,
		username = user1.username,
		email: String::from("montag@posteo.net"),
		sign_in_count: user1.sign_in_count,
	}
}

// With update syntax
let user2 = User {
	email: String::from("new_email@mail.com")
		..user1 // must come last to indicate that remaining fields are
}
```

> Note:
> The struct update syntax uses = like an assignment; this is because it moves the data, just as we saw in “Variables and Data Interacting with Move” on page 64. In this example, we can no longer use user1 after creating user2 because the String in the username field of user1 was moved into user2. If we had given user2 new String values for both email and username, and thus only used the active and sign_in_count values from user1, then user1 would still be valid after creating user2.

## Using Tuple Structs Without Named Fields to Create Different Types
Rust also uses tuple structs. They have the added meaning of the struct naming but no fields. Instead they use this notation; 

```rust
#[derive(Debug)]
struct Color(i32, i32, i32);
#[derive(Debug)]
struct Point(i32, i32, i32);

fn main() {
	let black = Color(0, 0, 0);
	let origin = Point(0, 0, 0);
	println!("{:?} {:?}", black, origin);
}
```

Each struct you define is its own type, even though the fields within the struct might have the same types. For example, a function that takes a parameter of type Color cannot take a Point as an argument, even though both types are made up of three i32 values.

## Unit-Like Structs
Unit-like structs can be useful when you need to implement a trait on some type but don’t have any data that you want to store in the type itself.

```rust
struct AlwaysEqual; // require more examples not understandable as such

fn main() {

	let subject = AlwaysEqual;
}

```

## Ownership of Struct Data and References
All struct examples deployed here hold text as a `string` and not as a sting slice `&str`. This is deliberate as we want the ownership of the underlying memory to be in sync with the validity of the struct. [[Rust Book Chapter 10]] introduce lifetimes that allow for references to be placed in `struct` objects.

## Adding Useful Functionality with Derived Traits

```rust
#[derive(debug)]

println!("rect1 is {:?}", rect1); // pretty print 1 
println!("rect1 is {:#?}",rect1); // pretty print 2

!dbg // also a macro to print out structures
```

## Method Syntax: `Enum` Adding Functionality to `Struct`
Methods are similar to functions: They are being declared with `fn` and a name, they can have parameters and a return value. They contain some code that’s run when the method is called from somewhere else. Unlike functions, methods are defined within the context of a struct (or an enum or a trait object, which we cover in [[Rust Book Chapter 6]] and [[Rust Book Chapter 17]], respectively), and their first parameter is always self, which represents the instance of the struct the method is being called on. 

### Defining Methods
To code a method for a struct we need to use the `impl` keyword:

```rust
#[derive(Debug)]
struct Rectangle {
	width: u32,
	height: u32,
}

impl Rectangle { // starts an implementation block; everything within impl is associated with Rectangle 
	fn area(&self) -> u32 {
	self.width * self.height
	}
}


fn main() {
	let rect = Rectangle {
		width: 30,
		height: 50,
		};

	println!(
		"The are of the rect is {} square pixels.", rect.area())
};
```

In the signature for area, we use `&self` instead of `rectangle: &Rectangle`. The &self is actually short for `self: &Self`. Within an `impl` block, the type Self is an alias for the type that the `impl` block is for. __Methods must have a parameter named `self` of type Self for their first parameter, so Rust lets you abbreviate this with only the name `self` in the first parameter spot.__ Note that we still need to use the & in front of the self shorthand to indicate that this method borrows the Self instance, just as we did in `rectangle: &Rectangle`. __Methods can take ownership of self, borrow self immutably, as we’ve done here, or borrow self mutably, just as they can any other parameter.__ If we wanted to change the instance that we’ve called the method on as part of what the method does, we’d use `&mut self` as the first parameter.

> Note: 
> Often, but not always, when we give methods with the same name as a field we want it to only return the value in the field and do nothing else. Methods like this are called getters, and Rust does not implement them automatically for struct fields as some other languages do. Getters are useful because you can make the field private but the method public, and thus enable read-only access to that field as part of the type’s public API.

### Methods with more parameters
```rust
fn main() {
	impl Rectangle {
    fn area(&self) -> u32 {
        self.width * self.height
    }

    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }
}
```