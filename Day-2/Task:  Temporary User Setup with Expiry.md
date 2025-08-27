## Senario Base Question:  Temporary User Setup with Expiry
As part of the temporary assignment to the Nautilus project, a developer named yousuf requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:

Create a user named yousuf on App Server 2 in Stratos Datacenter. Set the expiry date to 2023-12-07, ensuring the user is created in lowercase as per standard protocol.

# here’s how you can create the user yousuf on App Server 2 in Stratos Datacenter with the specified expiry date.

## Steps:

# 1. SSH into App Server 2

''' bash
ssh steve@hostname 
```
(Replace tony with the provided user if different.)

# 2. Create the user yousuf with expiry date
``` bash
sudo useradd -e 2023-12-07 yousuf
```
# 3. Verify the user was created with expiry date
``` 
sudo chage -l yousuf
```
# You should see:
```
Account expires    : Dec 07, 2023
```
