# 🦀 Rust Lab 7: Handling Errors Gracefully

## 🎯 Objective

Learn how to **handle** `Result` values properly by matching on success and error cases, instead of just returning them.

You’ll implement:

1. A helper function that performs safe division.
2. A top-level function that **handles** the error and returns a human-readable message.

---

## 🧩 Task

Implement these two functions in `src/lib.rs`:

````rust
/// Safely divides two numbers.
/// Returns `Ok(result)` if the division succeeds,
/// or `Err("division by zero")` if `b` is zero.
pub fn safe_divide(a: f64, b: f64) -> Result<f64, String> {
    // TODO: implement this
    Ok(0.0)
}

/// Calls `safe_divide` and returns a readable message.
///
/// # Example
/// ```
/// handle_division(10.0, 2.0); // -> "Result: 5"
/// handle_division(5.0, 0.0);  // -> "Error: division by zero"
/// ```
pub fn handle_division(a: f64, b: f64) -> String {
    // TODO: implement this using match or combinators
    String::new()
}
````

---

## 🧠 Expected Behavior

| Input         | Output                      |
| ------------- | --------------------------- |
| `(10.0, 2.0)` | `"Result: 5"`               |
| `(5.0, 0.0)`  | `"Error: division by zero"` |
| `(9.0, 3.0)`  | `"Result: 3"`               |

---

## 🚫 Requirements

* You **must** use `safe_divide` inside `handle_division`.
* Handle both `Ok` and `Err` cases using `match` (or `.map_or_else()` if you want bonus points).
* Do **not** panic or use `unwrap()`.
* Both functions must compile cleanly without warnings.

---

## 🧪 Tests

```rust
use lab6::{safe_divide, handle_division};

#[test]
fn test_safe_divide() {
    assert_eq!(safe_divide(10.0, 2.0), Ok(5.0));
    assert_eq!(safe_divide(5.0, 0.0), Err("division by zero".to_string()));
}

#[test]
fn test_handle_division() {
    assert_eq!(handle_division(10.0, 2.0), "Result: 5");
    assert_eq!(handle_division(9.0, 3.0), "Result: 3");
    assert_eq!(handle_division(5.0, 0.0), "Error: division by zero");
}
```

---

## Grading 

Submit your *lib.rs* to INGInious for grading.

---

## 🧱 Project Structure

```
lab6/
├── Cargo.toml
├── src/
│   └── lib.rs
└── tests/
    └── basic.rs
```

