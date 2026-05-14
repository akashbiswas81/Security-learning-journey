# Bandit Level 13 → Level 14 

This one is all about using an SSH key. The next password lives in `/etc/bandit_pass/bandit14`, but I can’t read that directly as my current user. Instead, the challenge hands me a private key that lets me SSH into `bandit14`.

---

## What I Learned

- SSH private key authentication
- Why ssh key file permissions matter
- How to log in with a key on a nonstandard port

---

## What I Did

I started by listing the files in the current directory and found the key file.

```bash
ls
```

The key was named `sshkey.private`. That’s the credential I needed to become `bandit14`.

I also checked the hint files, just in case the challenge had an extra note.

```bash
cat README
# or
cat hint
```

Then I fixed the key file permissions before trying to SSH. SSH won’t accept the key if it’s too open.

```bash
chmod 600 sshkey.private
```

That means the owner can read and write the file, but nobody else can access it.

After that, I connected with the key:

```bash
ssh -i sshkey.private bandit14@localhost -p 2220
```

The first time I connected, SSH asked:

```text
Are you sure you want to continue connecting?
```

I answered:

```text
yes
```

Then I was logged in as `bandit14`.

## What I Checked After Login

Once I had the shell, I read the password file:

```bash
cat /etc/bandit_pass/bandit14
```

That gave me the next level password.

## Command Notes

- `ls` to see the key file.
- `cat` to read hint files.
- `chmod 600 sshkey.private` to lock the key file down.
- `ssh -i sshkey.private bandit14@localhost -p 2220` to log in with the key.

## Why This Matters

This level is more about access than cracking anything. I learned how SSH key authentication works and why strict permissions are required for private keys.

## Personal Takeaway

This challenge felt like a good real-world admin task: find the key, secure it, and use it to get into the next account. It’s a nice reminder that security is often about the right workflow, not brute force.