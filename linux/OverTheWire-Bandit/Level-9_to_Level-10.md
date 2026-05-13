# Bandit Level 9 → Level 10

## Goal
Find the password hidden in readable strings that start with `===`.

---

## What I did
Used `strings data.txt | grep "==="` to extract and filter readable text from the file.

---

## Why it worked
`strings` pulls text out of a binary file.
`grep "==="` then finds the lines that contain the expected marker.

---

## Notes
- `strings` is useful when a file contains both binary and text data.
- `grep` narrows the output to the exact pattern I’m looking for.
- This is a common technique for recovering hidden text in CTF challenges.

---

## Takeaway
When the password is embedded in a binary file, use `strings` first, then filter for the pattern. It’s an efficient way to find hidden text.

---

## Password

```text
[REDACTED]
```