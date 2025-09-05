For Day 5: Script Execution Permissions in your 100 Days of DevOps (Practical Learning) series, let’s make a clear hands-on practice guide on Amazon Linux.

This topic will help your viewers understand file permissions, execution rights, and best practices for running scripts in Linux.

# Day 5 – Script Execution Permissions Linux

## Step 1: Create a Sample Script
```
cd ~
nano hello.sh
```
nano, vi, vim any text editor used to create a file
Inside the file:
```
#!/bin/bash
echo "Hello DevOps – Script Execution Permissions Test"
```
Save and exit

## Step 2: Check Script Permissions

```
ls -l hello.sh
```
Output example:
```
-rw-r--r-- 1 ec2-user ec2-user 56 Sep 5 12:00 hello.sh
```
rw- → owner can read/write
r-- → group can read
r-- → others can read
❌ No x → script not executable yet

## Step 3: Try to Execute Without Permissions
```
./hello.sh
```
You’ll see:
```
bash: ./hello.sh: Permission denied
```
## Step 4: Add Execute Permission
```
chmod +x hello.sh
```
ls -l hello.sh
```
Now:
```
-rwxr-xr-x 1 ec2-user ec2-user 56 Sep 5 12:00 hello.sh
```
✅ Now executable.

## Step 5: Run the Script
```
./hello.sh
```
Output:
```
Hello DevOps – Script Execution Permissions Test
```

Thanks
