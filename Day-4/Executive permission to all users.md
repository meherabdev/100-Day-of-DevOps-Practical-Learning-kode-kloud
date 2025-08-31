In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 2 within the Stratos Datacenter. Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 2. Additionally, ensure that all users have the capability to execute it. how to solve

1. Login to App Server 2

You’ll need to SSH into App Server 2 from the jump host (depending on your exam/lab setup).
For example:

ssh tony@stapp02


(Replace username and hostname with the correct ones for your lab — usually stapp02 is App Server 2 in KodeKloud-style tasks.)

2. Check if the script exists

Once logged in, confirm the script is present in /tmp:

ls -l /tmp/xfusioncorp.sh


You’ll likely see something like:

-rw-r--r--  1 root root  1234 Aug 31 12:00 /tmp/xfusioncorp.sh


Notice that only read/write permissions are present, no x (execute).

3. Add executable permissions for all users

Use chmod:

sudo chmod a+x /tmp/xfusioncorp.sh


a+x → adds execute (x) permission for all users (owner, group, others).

4. Verify permissions

Run:

ls -l /tmp/xfusioncorp.sh


You should now see:

-rwxr-xr-x  1 root root 1234 Aug 31 12:00 /tmp/xfusioncorp.sh


This means:

Owner (rwx) → can read, write, execute

Group (r-x) → can read, execute

Others (r-x) → can read, execute

So all users can now run the script.
