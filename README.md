# Multi-threaded File and Directory Search Tool

This is a multi-threaded C++ program designed to search for specific patterns within files and directories like the gerp command. It supports various command-line options to customize the search behavior, such as inverting the match, printing line numbers, and setting the maximum search depth.

## Features

- **Pattern Search**: Search for a specific pattern within files.
- **Directory Traversal**: Recursively search through directories up to a specified depth.
- **Multi-threading**: Utilizes multiple threads to speed up the search process.
- **Command-line Options**:
  - `-v`: Invert the sense of matching, to select non-matching lines.
  - `-n`: Prefix each line of output with the line number within its input file.
  - `-L`: Print the file name that does not contain the provided matching pattern.
  - `-f`: Search for the provided pattern in files and folders names.
  - `-d=`: Set the maximum search depth to the integer after `=` (e.g., `-d=3`).
  - `-th=`: Set the number of threads to the integer after `=` (e.g., `-th=6`).
