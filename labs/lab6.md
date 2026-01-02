# 🦀 Rust Lab 6: Error Handling with Result and Option

## 🎯 Objective

Learn to handle and propagate errors safely using Rust’s `Result` and `Option` types.
You’ll practice returning `Result` from functions, using the `?` operator, and handling errors gracefully.

---

## 🧩 Task

Implement the following function in `src/lib.rs`:

````rust
/// Safely divides two numbers.
/// Returns:
/// - Ok(result) if the division succeeds
/// - Err("division by zero") if `b` is zero
///
/// # Example
/// ```
/// safe_divide(10.0, 2.0); // -> Ok(5.0)
/// safe_divide(5.0, 0.0);  // -> Err("division by zero".to_string())
/// ```
pub fn safe_divide(a: f64, b: f64) -> Result<f64, String> {
    // TODO: implement this function
    Ok(0.0)
}
````

---

## 🧠 Expected Behavior

| Input         | Output                    |
| ------------- | ------------------------- |
| `(10.0, 2.0)` | `Ok(5.0)`                 |
| `(5.0, 0.0)`  | `Err("division by zero")` |
| `(-9.0, 3.0)` | `Ok(-3.0)`                |

---

## 🚫 Requirements

* Return a `Result<f64, String>`.
* Do **not** panic, unwrap, or print errors.
* Handle zero division explicitly using pattern matching or `if`.
* Code must compile without warnings.


---

## 🧪 Tests

```rust
use lab6::safe_divide;

#[test]
fn test_ok() {
    assert_eq!(safe_divide(10.0, 2.0), Ok(5.0));
    assert_eq!(safe_divide(-9.0, 3.0), Ok(-3.0));
}

#[test]
fn test_err() {
    assert_eq!(safe_divide(5.0, 0.0), Err("division by zero".to_string()));
}
```

---

##  Grading 

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

