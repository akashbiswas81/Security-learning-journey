# Bandit Level 12 → Level 13 

Level 12 to 13 was tricky but fun. The password is in `data.txt`, which is a hexdump of a file that's been compressed multiple times. I had to reverse the hexdump, then keep decompressing until I got to the plain text.

## What I Did

First, I created a temp directory to work in, since I didn't want to mess up the home folder.

```bash
mktemp -d
cd /tmp/tmp.something
```

Copied the data.txt over.

```bash
cp ~/data.txt .
```

Then, reversed the hexdump to get the binary file.

```bash
xxd -r data.txt > data
```

Checked what type it was.

```bash
file data
```

It was gzip compressed. So, renamed and unzipped.

```bash
mv data data.gz
gunzip data.gz
```

Checked again – now bzip2. Renamed and decompressed.

```bash
mv data data.bz2
bunzip2 data.bz2
```

Next was tar. Extracted it.

```bash
mv data data.tar
tar -xf data.tar
ls
```

There was another file inside. Kept going: check type, rename, extract. I think it was like 5 or 6 layers deep. Finally got to ASCII text.

```bash
cat data
```

And there was the password.

## Step-by-Step

1. **Temp directory**: Used mktemp to create a safe workspace. Didn't want to clutter up the bandit12 home.

2. **Copy file**: cp ~/data.txt . – brought it over.

3. **Reverse hexdump**: xxd -r to convert hex back to binary. Saved as 'data'.

4. **File type check**: 'file data' told me it was gzip. So, mv to data.gz and gunzip.

5. **Repeat**: Each time, check with file, rename based on type (.bz2 for bzip2, .tar for tar), and extract.

   - For gzip: gunzip
   - For bzip2: bunzip2
   - For tar: tar -xf

   After tar, there might be multiple files, so ls to see.

6. **Keep going**: I had to do this loop several times. It was nested compressions: gz inside bz2 inside tar, etc.

7. **Final extract**: When file said "ASCII text", cat it to get the password.

I got a bit confused with the renaming, but once I got the pattern, it was straightforward.

## Password for Level 13

[ANONYMIZED - Actual password not shown for security]

## What I Learned

- Hexdumps and reversing them with xxd.
- Multiple compression formats: gzip, bzip2, tar.
- Using 'file' command to detect file types.
- Working in temp directories for messy tasks.
- Persistence in unpacking nested archives.

This level taught me a lot about file formats and decompression. Felt like a real forensics challenge!

---

# Important Commands Learned

| Command | Purpose |
|---|---|
| `mktemp -d` | create temporary directory |
| `cp` | copy file |
| `mv` | rename file |
| `xxd -r` | reverse hexdump |
| `file` | identify file type |
| `gunzip` | extract gzip |
| `bunzip2` | extract bzip2 |
| `tar -xf` | extract tar archive |
| `ls` | list files |
| `cat` | read file |

---

# Concepts Learned

- Hexdump reversal
- Compression formats
- Recursive extraction
- File type detection
- Linux archive handling

These concepts are heavily used in:
- Cybersecurity
- CTFs
- Digital Forensics
- Malware Analysis
- Reverse Engineering