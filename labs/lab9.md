# 🦀 Rust Lab 9: Traits and Generics (with Multiple Trait Bounds)

## 🎯 Objective

Learn how to:

* Define and implement **multiple traits**.
* Write **generic functions** with **multiple trait bounds** (`T: TraitA + TraitB`).
* Use traits to express shared behavior across types.

By completing this lab, you’ll understand how Rust uses traits to achieve polymorphism — without inheritance.

---

## 🧩 Task

Implement the following in `src/lib.rs`:

```rust
/// A trait for calculating the area of a shape.
pub trait Area {
    fn area(&self) -> f64;
}

/// A trait for calculating the perimeter of a shape.
pub trait Perimeter {
    fn perimeter(&self) -> f64;
}

/// A rectangle type.
pub struct Rectangle {
    pub width: f64,
    pub height: f64,
}

/// A circle type.
pub struct Circle {
    pub radius: f64,
}

/// Implement both traits for both shapes.
impl Area for Rectangle {
    fn area(&self) -> f64 {
        // TODO
        0.0
    }
}

impl Perimeter for Rectangle {
    fn perimeter(&self) -> f64 {
        // TODO
        0.0
    }
}

impl Area for Circle {
    fn area(&self) -> f64 {
        // TODO
        0.0
    }
}

impl Perimeter for Circle {
    fn perimeter(&self) -> f64 {
        // TODO
        0.0
    }
}

/// A generic function that describes any shape implementing both Area and Perimeter.
/// Returns a formatted string:
/// "Area: X, Perimeter: Y"
pub fn describe_shape<T: Area + Perimeter>(shape: &T) -> String {
    // TODO
    String::new()
}
```

---

## 🧠 Expected Behavior

| Shape     | Input                 | Output (approx.)                        |
| --------- | --------------------- | --------------------------------------- |
| Rectangle | width=3.0, height=4.0 | `"Area: 12, Perimeter: 14"`             |
| Circle    | radius=2.0            | `"Area: 12.56637, Perimeter: 12.56637"` |

---

## 🚫 Requirements

* Define both traits: `Area` and `Perimeter`.
* Implement both traits for `Rectangle` and `Circle`.
* Use trait bounds (`T: Area + Perimeter`) in the `describe_shape` function.
* Must return a string in the format `"Area: X, Perimeter: Y"`.
* Use `std::f64::consts::PI` for circle calculations.
* Code must compile and run without warnings.

---

## 🧪 Tests

```rust
use lab9::{Area, Perimeter, Rectangle, Circle, describe_shape};

#[test]
fn test_rectangle() {
    let r = Rectangle { width: 3.0, height: 4.0 };
    assert!((r.area() - 12.0).abs() < 0.001);
    assert!((r.perimeter() - 14.0).abs() < 0.001);
    assert_eq!(describe_shape(&r), "Area: 12, Perimeter: 14");
}

#[test]
fn test_circle() {
    let c = Circle { radius: 2.0 };
    let a = c.area();
    let p = c.perimeter();
    assert!((a - 12.56637).abs() < 0.001);
    assert!((p - 12.56637).abs() < 0.001);
    assert!(describe_shape(&c).starts_with("Area: 12.56"));
}
```

---

## Grading 

Submit your *lib.rs* to INGInious for grading.

---

## 🧱 Project Structure

```
lab9/
├── Cargo.toml
├── src/
│   └── lib.rs
└── tests/
    └── basic.rs
```
