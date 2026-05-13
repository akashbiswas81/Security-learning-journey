# Bandit Cheatsheet

This cheatsheet summarizes the main commands and concepts I learned while playing OverTheWire Bandit levels 0–10.

## SSH Access

```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```

- `ssh`: connect securely to the remote Bandit server
- `-p 2220`: use port 2220 instead of the default SSH port

## Basic File Navigation

```bash
ls
cd <directory>
cat <file>
```

- `ls`: list files and directories in the current directory
- `cd inhere`: change into the `inhere` directory
- `cat readme`: display file contents on the terminal

## Working with Special Filenames

```bash
cat ./-
cat -- -
```

- Filenames starting with `-` may be parsed as options
- Use `./filename` or `-- filename` to force the shell to treat the text as a file path

## Handling Spaces and Special Characters in Filenames

```bash
cat -- "--spaces in this filename--"
```

- `--` stops option parsing for many GNU commands
- Quote filenames that contain spaces so the shell treats them as one argument

## Finding Hidden Files

```bash
ls -a
```

- `ls -a` shows hidden files and directories that start with `.`
- Hidden files are not truly secret, they are just omitted by default

## Identifying File Types

```bash
file ./*
```

- `file` inspects each file and reports its type
- Useful for finding which files are human-readable and which are binary

## Searching by File Attributes

```bash
find . -type f -size 1033c ! -executable
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

- `find .`: search from the current directory recursively
- `-type f`: match regular files only
- `-size 1033c`: match files exactly 1033 bytes in size
- `! -executable`: exclude executable files
- `2>/dev/null`: remove permission denied errors from output

## Pattern Search in Text Files

```bash
grep "millionth" data.txt
```

- `grep`: search for text patterns inside files
- Works well for finding a specific keyword or phrase

## Text Processing and Unique Lines

```bash
sort data.txt | uniq -u
```

- `sort`: order lines so duplicates become adjacent
- `uniq -u`: print only lines that appear exactly once
- Useful for finding the unique or odd line out

## Extracting Readable Strings from Binary Files

```bash
strings data.txt | grep "==="
```

- `strings`: extract printable characters from binary files
- Helps locate hidden text or passwords embedded in binaries

## Useful Notes

- Always inspect the directory first with `ls` before running commands.
- Use `cat` for plain text files, but verify the file type first if the filename looks unusual.
- If a command has a filename argument that could be confused with an option, use `--`.
- For CTF-style challenges, combine simple commands into a pipeline to isolate the answer efficiently.

---

## Summary

This file is meant to be a quick reference for the Bandit commands I used most often. It covers SSH access, file discovery, special filename handling, permission-safe searching, and text extraction.
