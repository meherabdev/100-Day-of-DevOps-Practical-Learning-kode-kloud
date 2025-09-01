
Setup Lab Environment

SSH your task user (get all info to click to get data)


# Linux User Setup with Non-Interactive Shell

This guide shows how to create Linux users with **non-interactive shells**, ideal for SFTP-only accounts, automation users, or restricted access scenarios.

---

## 1. Create a User with a Non-Interactive Shell

Use `/sbin/nologin` or `/bin/false` as the login shell:

```
# Syntax
sudo useradd -s /sbin/nologin <username>
```

# Example
```
sudo useradd -s /sbin/nologin testuser
```

## 2. Verify the User

Check the assigned shell:

```
sudo grep testuser /etc/passwd
```
Expected output:

```
testuser:x:1001:1001::/home/testuser:/sbin/nologin
```