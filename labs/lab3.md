# 🦀 Rust Lab 2: Ownership and Borrowing

## 🎯 Objective

Practice Rust’s **ownership** and **borrowing** system by implementing a function that analyzes text **without taking ownership** of it.

You will:

* Pass a borrowed string slice (`&str`) to a function.
* Return a new owned `String` value.
* Avoid unnecessary cloning or moves.

---

## 🧩 Task

Implement the following function in `src/lib.rs`:

````rust
/// Analyzes the given text and returns a formatted summary as a `String`.
///
/// # Arguments
/// * `text` - A borrowed string slice (`&str`)
///
/// # Returns
/// A `String` formatted as "Words: X, Characters: Y"
///
/// # Example
/// ```
/// word_stats("hello world"); // -> "Words: 2, Characters: 11"
/// ```
pub fn word_stats(text: &str) -> String {
    // TODO: implement this function
    String::new()
}
````

---

## 🧠 Expected Output

| Input                   | Output                       |
| ----------------------- | ---------------------------- |
| `"hello world"`         | `"Words: 2, Characters: 11"` |
| `"Rust is great"`       | `"Words: 3, Characters: 13"` |
| `""`                    | `"Words: 0, Characters: 0"`  |
| `"  Rust   is great  "` | `"Words: 3, Characters: 17"` |

Count **all characters**, including spaces.
Words are separated by one or more whitespace characters.

---

## 🚫 Requirements

* The function signature **must** be:

  ```rust
  pub fn word_stats(text: &str) -> String
  ```
* Do **not** take ownership of the input (`String`) or clone it unnecessarily.
* Do **not** print anything with `println!()`.
* Your code must **compile without warnings**.

---

## 🧾 Tests

The following tests will be run automatically by the autograder:

```rust
use ownership_lab::word_stats;

#[test]
fn test_basic() {
    assert_eq!(word_stats("hello world"), "Words: 2, Characters: 11");
}

#[test]
fn test_empty() {
    assert_eq!(word_stats(""), "Words: 0, Characters: 0");
}

#[test]
fn test_extra_spaces() {
    assert_eq!(word_stats("  Rust   is great  "), "Words: 3, Characters: 17");
}

#[test]
fn test_no_spaces() {
    assert_eq!(word_stats("palindrome"), "Words: 1, Characters: 10");
}
```

---

## Grading 

Submit your lib.rs file to INGInious for grading.

---

## 🧱 Project Structure

```
ownership_lab/
├── Cargo.toml
├── src/
│   └── lib.rs
└── tests/
    └── basic.rs
```

---

## 🌟 Optional Extension

Write a second function that **takes ownership** instead of borrowing:

```rust
pub fn shout(mut text: String) -> String {
    text.push_str("!!!");
    text.to_uppercase()
}
```

Try calling it with a variable:

```rust
let my_string = String::from("rust");
let result = shout(my_string);
println!("{}", result);
// println!("{}", my_string); // ❌ Compiler error: value moved
```

Explain in a comment why Rust prevents you from using `my_string` after the move.
