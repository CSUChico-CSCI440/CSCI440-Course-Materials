# 🦀 Rust Lab 4: Ownership, Borrowing, and Lifetimes (Helper Functions)

## 🎯 Objective

Build on your understanding of **ownership**, **borrowing**, and **lifetimes** by writing a program with **two functions**:

* One function to find the longest word in a sentence (returns a reference).
* One function to summarize the sentence using that helper function (returns an owned string).

This lab reinforces how data moves, how references borrow safely, and how Rust prevents invalid references.

---

## 🧩 Task

Implement the following two functions in `src/lib.rs`:

````rust
/// Returns a reference to the longest word in the given text.
/// If there are multiple longest words, return the last one.
///
/// # Example
/// ```
/// longest_word("Rust makes memory safety easy"); // -> "memory"
/// ```
pub fn longest_word(text: &str) -> &str {
    // TODO: implement this function
    ""
}

/// Returns a summary string in the format:
/// "Longest word: X (Y characters)"
///
/// This function should call `longest_word()` to get the result,
/// then build and return a new owned `String`.
///
/// # Example
/// ```
/// summarize_longest_word("Rust is fearless"); // -> "Longest word: fearless (8 characters)"
/// ```
pub fn summarize_longest_word(text: &str) -> String {
    // TODO: implement this function using `longest_word()`
    String::new()
}
````

---

## 🧠 Expected Behavior

| Input                       | Output                                     |
| --------------------------- | ------------------------------------------ |
| `"Rust is fast"`            | `"Longest word: fast (4 characters)"`      |
| `"Ownership and borrowing"` | `"Longest word: borrowing (9 characters)"` |
| `"Hi"`                      | `"Longest word: Hi (2 characters)"`        |
| `""`                        | `"Longest word:  (0 characters)"`          |

---

## 🚫 Requirements

* The helper function `longest_word` must:

  * Take a borrowed `&str` as input.
  * Return a borrowed `&str` (no clones or ownership moves).
  * Not allocate or modify the input string.
* The summary function `summarize_longest_word` must:

  * Borrow the input.
  * Call `longest_word`.
  * Return an owned `String`.
* Do **not** use `println!()` inside the functions.
* Code must **compile cleanly** without lifetime errors or warnings.

---


## 🧾 Tests (used for autograding)

```rust
use lab4::longest_word;
use lab4::summarize_longest_word;

#[test]
fn test_longest_word_basic() {
    assert_eq!(longest_word("Rust is fast"), "fast");
    assert_eq!(longest_word("Ownership and borrowing"), "borrowing");
    assert_eq!(longest_word("Hi"), "Hi");
}

#[test]
fn test_summarize() {
    assert_eq!(summarize_longest_word("Rust is fast"), "Longest word: fast (4 characters)");
    assert_eq!(summarize_longest_word("Ownership and borrowing"), "Longest word: borrowing (9 characters)");
    assert_eq!(summarize_longest_word(""), "Longest word:  (0 characters)");
}
```

---

## Grading

Submit your *lib.rs* to INGInious for grading

---

## 🧱 Project Structure

```
lab4/
├── Cargo.toml
├── src/
│   └── lib.rs
└── tests/
    └── basic.rs
```

