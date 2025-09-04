Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. To initiate testing, the following requirements have been established for App server 2 in the Stratos Datacenter:



Install the required SELinux packages.

Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.

No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.

Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.

Steps to Perform
# 1. Login to App Server 2
```
ssh tony@<APP_SERVER_2_IP>
```

# 2. Install required SELinux packages

```
sudo yum install -y selinux-policy selinux-policy-targeted policycoreutils
```
On Ubuntu/Debian systems:

```
sudo apt update
sudo apt install -y selinux-utils selinux-basics policycoreutils
```
# 3 Check SELinux current status
```
sestatus
```
This may show enabled or disabled. You don’t need to worry about the current status—only the permanent configuration matters.

# 4 Permanently disable SELinux
    Edit the SELinux config file:
```
sudo vi /etc/selinux/config
```
Find this line:
```
SELINUX=enforcing
```
Change it to:
```
SELINUX=disabled
```
# 5 Verify the configuration change
```
grep SELINUX= /etc/selinux/config

```
Expected output:
```
SELINUX=disabled
```

# 6 Do not reboot now (since reboot is already scheduled). After reboot, SELinux will be disabled automatically.
