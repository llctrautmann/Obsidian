---
title: Format! Macro in Rust
date: 29-01-2024
time: 19:21
author: Luca Trautmann
tags: 
series: Rust
chapter: "19"
---
# Format! Macro in Rust
## Decimal to Hexadecimal

To convert a decimal integer to a hexadecimal string, you can use the `format!` macro with the `x` specifier:

```rust
fn main() {  
    let decimal_number = 19035;  
    let hex_string = format!("{:x}", decimal_number);  
    println!("The hexadecimal representation of {} is 0x{}", decimal_number, hex_string);  
}
```












