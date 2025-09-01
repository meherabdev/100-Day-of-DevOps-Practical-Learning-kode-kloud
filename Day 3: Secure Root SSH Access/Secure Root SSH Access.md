#Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login. 

#Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

#Here are the exact steps you should follow on each app server:

# 1. Switch to root user
```
sudo su -
```
# 2. Open the SSH configuration file
```
vi /etc/ssh/sshd_config
```
# 3. Find and update the following directive:

Locate this line (it may be commented out):

PermitRootLogin yes


# Change it to:

PermitRootLogin no


(If the line doesn’t exist, just add it at the end of the file.)

# 4. Restart the SSH service

On CentOS/RHEL:
```
sudo systemctl restart sshd
```

On Ubuntu/Debian:
```
sudo systemctl restart ssh
```
# 5. Verify changes

Run:
```
sshd -T | grep permitrootlogin
```

You should see:

permitrootlogin no


🔒 This ensures root cannot directly SSH into the server. Instead, users must log in with their own accounts and use sudo for administrative tasks.