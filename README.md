# learn-linux
---
# Linux CLI & Core Fundamentals

## 1. Terminal vs. Shell

* **Terminal:** The graphical user interface (GUI) application where you type your inputs.
* **Shell:** The command-line interpreter  that takes your input and sends it to the **Linux Kernel** for execution.

### Prompts

* `$` — Standard user environment.
* `#` — Root (Administrator/Superuser) environment.

---

## 2. File System Architecture

Linux uses a single hierarchical tree structure starting from the root directory:

```text
/ (Root)
├── bin/        (Essential user binaries)
├── etc/        (System configuration files)
├── home/       (User home directories)
│   └── user/
├── var/        (Variable data like logs)
└── usr/        (User programs and data)

```

---

## 3. Basic Commands & File Operations

### Directory Navigation & Creation

* **`pwd`** — Print Working Directory (shows your current location).
* **`cd [path]`** — Change to a different directory.
* **`mkdir [dir]`** — Create a new directory.
* `-p` — Create parent directories as needed without throwing errors.
* `-v` — Verbose mode; prints a message for each directory created.



### Listing Files (`ls`)

* **`ls`** — List directory contents.
* `-a` — Show all files (including hidden files starting with `.`).
* `-l` — Display long-format list (permissions, owner, size, modification date).
* `-h` — Display human-readable file sizes (used with `-l`, e.g., 1K, 234M, 2G).
* `-r` — Reverse the sort order.
* `-t` — Sort by modification time (newest first).
* `-S` — Sort by file size (largest first).



### File Operations

* **`touch [filename]`** — Create an empty file or update access/modification timestamps.
* **`echo "[text]"`** — Print text to stdout or append/redirect it into a file.
* **`file [filename]`** — Determine file type independently of its file extension.
* *Example:* `file *.txt` (inspects all files ending in `.txt`).


* **`mv [source] [destination]`** — Move or rename files and directories.
* `-i` — Interactive mode; prompts before overwriting.
* `-n` — Do not overwrite an existing destination file.
* `-t [dir]` — Move target directory before source files (`mv -t /target/dir file1 file2`).



---

## 4. Reading & Viewing Files

* **`cat [file]`** — Concatenate and display file content.
* *Example:* `cat file1.txt file2.txt > combined.txt` (merges two files into a third).


* **`head [file]`** — Display the first 10 lines of a file.
* **`tail [file]`** — Display the last 10 lines of a file.
* **`nl [file]`** — Print file contents with line numbers attached to every line.

---

## 5. Command History Tricks

* **`history`** — View the list of previously executed commands.
* **`!!`** — Re-run the most recent command.
* **`![number]`** — Execute a specific command number from your history (e.g., `!102`).
* **`![prefix]`** — Execute the most recent command starting with the given string (e.g., `!cat`).

---

## 6. Text Processing & Data Streams

### System Concepts

* **File Descriptor:** An abstract indicator (handle) used by an operating system to access standard I/O streams or files (`0` for stdin, `1` for stdout, `2` for stderr).

### Utility Commands

* **`find`** — Search for files and directories within a file hierarchy.
* `find . -type d` — Find directories only.
* `find . -type f` — Find regular files only.


* **`grep [pattern]`** — Search text using matching patterns.
* **`sort`** — Sort lines of text files alphabetically or numerically.
* **`uniq`** — Filter out or report adjacent duplicate lines (usually run after `sort`).
* **`tr`** — Translate, squeeze, or delete specific characters from standard input (`stdin`).
* **`wc`** — Print line, word, and byte/character counts for files.
* **`apropos [keyword]`** — Search manual pages for short descriptions matching a keyword.
