# 🦀 Rust Lab 8: Collections and Iterators

## 🎯 Objective

Learn to use **collections** and **iterators** to process text efficiently.
You’ll count the frequency of each word in a given string and return the results in a formatted string.

You’ll practice:

* Creating and updating a `HashMap`.
* Iterating over text with `.split_whitespace()`.
* Using `.entry()` and `.or_insert()` for counting.
* Converting a collection into a formatted string using iterator combinators.

---

## 🧩 Task

Implement the following function in `src/lib.rs`:

````rust
use std::collections::HashMap;

/// Counts the frequency of each word in the input text.
///
/// Returns a formatted string like:
/// "hello: 2, world: 1"
///
/// The order of words in the output does not matter.
///
/// # Example
/// ```
/// word_frequency("hello world hello"); // -> "hello: 2, world: 1"
/// ```
pub fn word_frequency(text: &str) -> String {
    // TODO: implement this function
    String::new()
}
````

---

## 🧠 Expected Behavior

| Input                     | Output (order may vary)                      |
| ------------------------- | -------------------------------------------- |
| `"hello world hello"`     | `"hello: 2, world: 1"`                       |
| `"rust is fast and safe"` | `"rust: 1, is: 1, fast: 1, and: 1, safe: 1"` |
| `""`                      | `""`                                         |

> Output can be in any order — autograder checks normalized results.

---

## 🚫 Requirements

* Use a `HashMap<String, usize>` to count word occurrences.
* Use iterators and combinators (no manual loops with indices).
* Avoid unnecessary `clone()` or `collect()` unless required.
* Must compile and run without warnings.


---

## 🧪 Tests

```rust
use lab8::word_frequency;

fn normalize(s: &str) -> Vec<String> {
    let mut parts: Vec<String> = s.split(", ").map(|x| x.to_string()).collect();
    parts.sort();
    parts
}

#[test]
fn test_basic() {
    let result = word_frequency("hello world hello");
    assert_eq!(normalize(&result), normalize("hello: 2, world: 1"));
}

#[test]
fn test_multiple_words() {
    let result = word_frequency("rust is fast and safe");
    assert_eq!(
        normalize(&result),
        normalize("rust: 1, is: 1, fast: 1, and: 1, safe: 1")
    );
}

#[test]
fn test_empty() {
    let result = word_frequency("");
    assert_eq!(result, "");
}
```

---

## Grading 

Submit your *lib.rs* to INGInious for grading.

---

## 🧱 Project Structure

```
lab8/
├── Cargo.toml
├── src/
│   └── lib.rs
└── tests/
    └── basic.rs
```
