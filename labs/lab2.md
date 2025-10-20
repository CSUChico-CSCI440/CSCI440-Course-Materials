# 🔤 Rust Assignment: String Palindrome Checker

## 🎯 Objective

Write a Rust program that determines whether a given **word or phrase** is a palindrome — that is, it reads the same forward and backward (like `racecar` or `madam`).

This exercise helps you practice:

* Basic string input and manipulation
* Loops and conditionals
* Comparing strings
* Simple use of standard library functions

> 💡 This version focuses on **strings**, not numbers, so you won’t need to worry about borrowing or lifetimes yet.

---

## 📋 Instructions

1. Ask the user to enter a word or phrase.
2. Convert the input to lowercase so the check is case-insensitive.
3. (Optional) Remove spaces so multi-word phrases like “never odd or even” count as palindromes.
4. Check if the string is the same forwards and backwards.
5. Print whether it’s a palindrome or not.

---

## 🧠 Example Runs

```
Enter text: racecar
"racecar" is a palindrome!
```

```
Enter text: Rust
"Rust" is not a palindrome.
```

```
Enter text: Never odd or even
"Never odd or even" is a palindrome!
```

---

## 🧩 Hints

* Use `.trim()` to remove the newline from input.
* Convert to lowercase with `.to_lowercase()`.
* You can reverse a string easily:

  ```rust
  let reversed: String = text.chars().rev().collect();
  ```
* Compare the cleaned string with its reversed version:

  ```rust
  if text == reversed {
      println!("It's a palindrome!");
  }
  ```

---


## ✅ Grading 

Submit your solution to INGInious for grading.


**Have fun checking palindromes! 🪞**


