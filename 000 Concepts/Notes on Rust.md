---
title: Notes on Rust
date: 06-01-2024
time: 15:07
author: Luca Trautmann
tags: 
series: 
chapter:
---

# Notes on Rust
## Structs, Enums and Impl
### Structs
Structs are collections of datatypes that have a connection with each other. For example the coordinates of an object in space could be defined as such:

```Rust
struct Coordinates { // Convention dicates Camel case
	x: i32,
	y: i32,
}

fn main() {
	let point = Coordinates { x: 0, y: 1 };

	// To print a value we use dot-notation
	println!("{:#?}", point.x); // returns 0
	println!("{:#?}", point.y); // returns 1
	// To update a field in the struct we also use dot-notation

	let mut point = point; // make the variable mutable
	point.x = 5;
	println!("{:?}", point.x); // returns 5

}
```


```Rust
// A `struct` can include `..` to indicate that you want to use a copy of some other `struct` for some of the values

struct Point3d {
    x: i32,
    y: i32,
    z: i32,
}

let mut point = Point3d { x: 0, y: 0, z: 0 };
point = Point3d { y: 1, .. point };
}
```









