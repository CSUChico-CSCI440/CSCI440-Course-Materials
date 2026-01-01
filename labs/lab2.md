# 🦀 Rust Lab 2: String Palindrome Checker (Function-Based)

## 🎯 Objective

Write a Rust **function** that determines whether a given **word or phrase** is a palindrome — that is, it reads the same forward and backward (like `racecar` or `madam`).

This lab focuses on writing **testable, reusable code** instead of interactive programs.

You will practice:

* Basic string manipulation
* Iteration over characters
* Comparing values
* Writing functions suitable for automated testing

> 💡 This version avoids user input (`stdin`) so it can be graded automatically using Rust’s test framework.

---

## 🧩 Task

Implement the following function in `src/lib.rs`:

````rust
/// Returns true if the given text is a palindrome.
///
/// The comparison should be case-insensitive.
/// Spaces should be ignored.
///
/// # Examples
/// ```
/// is_palindrome("racecar") -> true
/// is_palindrome("Rust") -> false
/// is_palindrome("Never odd or even") -> true
/// ```
pub fn is_palindrome(text: &str) -> bool {
    // TODO: implement this function
    false
}
````

---

## 🧠 Requirements

Your function must:

1. Treat uppercase and lowercase letters as equal.
2. Ignore spaces in the input.
3. Return `true` if the cleaned string is a palindrome, `false` otherwise.
4. **Not** print anything (`println!` is not allowed).
5. Compile without warnings.

---

## 🧠 Examples

| Input                 | Return Value |
| --------------------- | ------------ |
| `"racecar"`           | `true`       |
| `"Rust"`              | `false`      |
| `"Never odd or even"` | `true`       |
| `"hello world"`       | `false`      |
| `""`                  | `true`       |

---

## 🧩 Hints

* Convert the input to lowercase:

  ```rust
  let lower = text.to_lowercase();
  ```
* Remove spaces:

  ```rust
  let cleaned: String = lower.chars().filter(|c| !c.is_whitespace()).collect();
  ```
* Reverse the string:

  ```rust
  let reversed: String = cleaned.chars().rev().collect();
  ```
* Compare the original and reversed versions.

---

## 🧪 Testing

Your code will be tested automatically using Rust’s test framework.

Example test cases (provided by the autograder):

```rust
use lab2::is_palindrome;

#[test]
fn test_basic_palindromes() {
    assert!(is_palindrome("racecar"));
    assert!(is_palindrome("Never odd or even"));
}

#[test]
fn test_non_palindromes() {
    assert!(!is_palindrome("Rust"));
    assert!(!is_palindrome("hello world"));
}

#[test]
fn test_edge_cases() {
    assert!(is_palindrome(""));
    assert!(is_palindrome("a"));
}
```

---

## 📁 Project Structure

Your project will follow this structure:

```
lab2/
├── Cargo.toml
├── src/
│   └── lib.rs        # You implement is_palindrome here
└── tests/
    └── basic.rs      # Autograder tests (read-only)
```

* You should **only modify `src/lib.rs`**.
* You will **not** submit a `main.rs`, but if you want to make one to test, you can.
* The autograder will run:

  ```
  cargo test --tests --quiet
  ```

---

## ✅ Submission

Submit your *lib.rs* solution to **INGInious**.
Make sure your code compiles and all tests pass.

---

**Have fun checking palindromes! 🪞**
