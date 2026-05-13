# Bandit Cheatsheet

This cheatsheet summarizes the main commands and concepts I learned while playing OverTheWire Bandit levels 0–10. The table format makes it easy to add more commands as I progress.

## Command Reference

| Command | Purpose | Notes / Example |
|---|---|---|
| `ssh -p 2220 bandit0@bandit.labs.overthewire.org` | Connect to the Bandit server | Use port `2220` instead of default SSH port |
| `ls` | List files and directories | Start with `ls` to inspect the current directory |
| `cd <directory>` | Change directory | Example: `cd inhere` |
| `cat <file>` | Display contents of a text file | Example: `cat readme` |
| `cat ./-` | Read a file named `-` | `./` prevents the shell from treating `-` as an option |
| `cat -- -` | Read a file named `-` | `--` stops option parsing |
| `cat -- "--spaces in this filename--"` | Read a file with spaces and special characters in its name | Quote the filename to preserve spaces |
| `ls -a` | Show all files, including hidden ones | Hidden files start with `.` |
| `file ./*` | Inspect file types in the directory | Use before reading unknown files |
| `find . -type f -size 1033c ! -executable` | Find files that are regular, exactly 1033 bytes, and not executable | Good for filtering by size and permissions |
| `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` | Find a file by owner, group, size from root | `2>/dev/null` hides permission denied errors |
| `grep "millionth" data.txt` | Search for a pattern in a text file | `grep` is the basic tool for text searching |
| `sort data.txt | uniq -u` | Find the unique line in a file | Sort first, then `uniq -u` keeps only non-duplicate lines |
| `strings data.txt | grep "==="` | Extract readable strings from binary data and filter by pattern | Useful for hidden text inside binary files |

