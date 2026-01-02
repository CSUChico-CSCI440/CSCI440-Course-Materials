# 🦀 Rust Lab 5: Data Structures and Pattern Matching

## 🎯 Objective

Learn to use **structs**, **enums**, and **pattern matching** to model real-world data.

You will:

* Define a `Shape` enum with multiple variants.
* Implement a function to compute area using `match`.
* Reinforce ownership, immutability, and type safety.

---

## 🧠 Task

Implement the following enum and function in `src/lib.rs`:

````rust
/// Represents geometric shapes.
pub enum Shape {
    Circle(f64),        // radius
    Rectangle(f64, f64),// width, height
    Square(f64),        // side length
}

/// Computes the area of a given shape.
///
/// # Example
/// ```
/// area(Shape::Circle(2.0)); // -> 12.566370...
/// ```
pub fn area(shape: Shape) -> f64 {
    // TODO: implement using `match`
    0.0
}
````

---

## 🧾 Expected Behavior

| Input                        | Output (approx.) |
| ---------------------------- | ---------------- |
| `Shape::Circle(2.0)`         | `12.566370`      |
| `Shape::Rectangle(3.0, 4.0)` | `12.0`           |
| `Shape::Square(5.0)`         | `25.0`           |

> You can use `std::f64::consts::PI` for circle area.
> Use simple formulas for the others.

---

## 🚫 Requirements

* Use a `match` expression to destructure each variant.
* Return an `f64` area.
* Do not use `if`/`else` — only `match`.
* Code must compile without warnings.


---

## 🧪 Tests

```rust
use lab5::{Shape, area};

#[test]
fn test_circle() {
    let result = area(Shape::Circle(2.0));
    assert!((result - 12.56637).abs() < 0.001);
}

#[test]
fn test_rectangle() {
    assert_eq!(area(Shape::Rectangle(3.0, 4.0)), 12.0);
}

#[test]
fn test_square() {
    assert_eq!(area(Shape::Square(5.0)), 25.0);
}
```

---

## Grading 

Submit your *lib.rs* to INGInious for grading.

---

## 🧱 Project Structure

```
lab5/
├── Cargo.toml
├── src/
│   └── lib.rs
└── tests/
    └── basic.rs
```

