# Grep

This is a multi-threaded C++ program designed to search for specific patterns within files and directories similar to Unix `grep`. It supports various command-line options to customize the search behavior, such as inverting the match, printing line numbers, and setting the maximum search depth.

---

## Compilation

To compile the program, use the following command:

```bash
g++ -std=c++17 -pthread -o search grep.cpp
```

---

## Usage

```bash
./search [OPTIONS] "PATTERN" [FILES]
```
---

### Options

| Option | Description |
|--------|--------------|
| `-v` | Invert match — select lines that **do not** match the pattern. |
| `-n` | Prefix each line of output with its **line number**. |
| `-L` | Print file names that **do not contain** the matching pattern. |
| `-f` | Search for the pattern in **file and folder names** instead of contents. |
| `-d=N` | Set the **maximum directory search depth** (default: `4`). |
| `-th=N` | Set the **number of threads** (default: number of CPU cores). |

> **Note:** If `-f` is enabled, the `[FILES]` argument is **not required**.

---

## Multithreading Details

- Each thread searches independently through directories in a shared queue.
- Synchronization is managed using **mutex locks** and **condition variables**.
- The number of threads defaults to your **CPU core count**, but can be overridden.

---
