# Random Rust notes

> randomly jot down things i learn in rust till i am ready to organize them

## Err(_)

used inside a match expression, the underscore `_` signifies a `catch-all` meaning it should run the resulting code for
any type of error

## Type annotation

in the statement 

```rs
let guess: u32 = "4".parse()
```

`: u32` is the `type annotation`