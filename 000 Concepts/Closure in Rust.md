---
title: Closure in Rust
date: 29-01-2024
time: 19:38
author: Luca Trautmann
tags:
  - Code
series: Rust
chapter: "20"
---
# Closure in Rust (code example)

```rust
// Function to ensure that a value is within the range [0, 255]
fn rounding(val: i32) -> i32 {
    if val < 0 {
        0
    } else if val > 255 {
        255
    } else {
        val
    }
}

// Function to convert RGB values to a concatenated uppercase hexadecimal string
fn rgb(r: i32, g: i32, b: i32) -> String {
    // Create an array with RGB values and iterate over each element
    let hex_values = [r, g, b]
        .iter()
        // For each value, format it as a two-digit uppercase hexadecimal and collect into a Vec<String>
        .map(|&value| format!("{:02X}", rounding(value)))
        .collect::<Vec<String>>()
        // Join the Vec<String> into a single String
        .join("");

    // Return the concatenated uppercase hexadecimal string
    hex_values
}

// IDEAL SOLUTION
fn rgb(r: i32, g: i32, b: i32) -> String {
    format!(
        "{:02X}{:02X}{:02X}",
        r.clamp(0, 255),
        g.clamp(0, 255),
        b.clamp(0, 255)
    ) 
}
```

The `|&value|` is a syntax in Rust used for destructuring the elements when iterating over an array or any iterable. Let's break it down:

1. **`&value`**: This part is creating a reference to each element in the array. The `&` symbol is used to create a reference to the element, and `value` is the name of the variable representing that reference.

2. **`| ... |`**: This part is the syntax for a __closure__ in Rust. A closure is an anonymous function. The variables inside the pipes (`| ... |`) are the parameters of the closure.

When you combine them, `|&value|` means that for each element in the array, it is creating a reference to that element and passing it to the closure. The closure then uses the variable name `value` to refer to each individual element within its scope.

In the provided code snippet:

```rust
.map(|&value| format!("{:02X}", rounding(value)))
```

This part is part of the `.map()` function, where for each element in the array, it's formatting the element (converted to uppercase hexadecimal using `format!("{:02X}", rounding(value))`). The `|&value|` is used to destructure the elements while iterating over them.

This is often done to avoid ownership issues; it borrows the element rather than taking ownership of it. In this case, since we're only reading from the elements and not modifying them, borrowing with `&` is appropriate and more efficient than taking ownership.










