# minigrep

**A simplified command-line utility for searching files, implemented in Rust.**

This repository contains an implementation of the `minigrep` project from **Chapter 12: An I/O Project: Building a Command Line Program** of *The Rust Programming Language* book. It serves as an educational example to demonstrate Rust's capabilities for I/O, modularity, error handling, and testing in a real-world command-line application context. It mimics the core functionality of the Unix `grep` utility.

---

## 🚀 Features

* **Argument Parsing:** Handles command-line arguments for the search query and the file path.
* **Modular Codebase:** Organizes code into separate modules (e.g., `Config` struct and the main `run` function) for clarity and testability.
* **Error Handling:** Uses `Result<T, E>` to propagate errors (like file not found or invalid arguments) instead of crashing (`panic!`).
* **Core Search Logic:** Implements both **case-sensitive** (default) and **case-insensitive** searching.
* **Environment Variable Support:** Search behavior can be toggled to be case-insensitive using the `CASE_INSENSITIVE` environment variable.

---

## 🛠️ Installation and Setup

### Prerequisites

You must have **Rust** and **Cargo** installed on your system.

### Compiling and Running

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/jackgris/minigrep.git](https://github.com/jackgris/minigrep.git)
    cd minigrep
    ```

2.  **Build the executable:**
    ```bash
    cargo build --release
    ```
    The executable will be located at `target/release/minigrep`.

---

## 💡 Usage

The application is run via **Cargo** or directly with the compiled binary, requiring two arguments: a search query and a file path.

### Basic Syntax

```bash
minigrep <QUERY> <FILEPATH>
```
## Examples

### 1. Case-Sensitive Search (Default)

This command searches for the literal string `safe` in the file `lorem_ipsum.txt`.

```bash
cargo run -- safe lorem_ipsum.txt
```

## 2. Case-Insensitive Search

The search can be made case-insensitive by setting the `CASE_INSENSITIVE` environment variable.

### On Linux/macOS (Bash)

```bash
# Finds "to", "To", and "TO"
CASE_INSENSITIVE=1 cargo run -- to poem.txt
```

### 3. Handling Errors

If you provide fewer than two arguments, the program will return a custom error message instead of crashing:

```bash
# Error: Not enough arguments
cargo run --
```
## 🧪 Testing

Unit tests are included to verify the correct behavior of the core searching functions, ensuring that case-sensitive and case-insensitive searches return the expected results.

To run all defined tests:

```bash
cargo test
```
## 📚 Acknowledgements

This project is a direct implementation and study aid based on:

> *The Rust Programming Language* (Second Edition)
> by **Steve Klabnik** and **Carol Nichols**.
