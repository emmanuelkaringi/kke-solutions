# Task Description
In a bid to automate backup processes, the `xFusionCorp Industries` sysadmin team has developed a new bash script named `xfusioncorp.sh`. While the script has been distributed to all necessary servers, it lacks executable permissions on `App Server 2` within the Stratos Datacenter.

a. Your task is to grant executable permissions to the `/tmp/xfusioncorp.sh` script on `App Server 2`. Additionally, ensure that all users have the capability to execute it.

# Solution
1. Login or SSH into `App server 1`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Grant executable permissions to the `/tmp/xfusioncorp.sh` script.

    `chmod o+rx /tmp/xfusioncorp.sh` OR `chmod 006 /tmp/xfusioncorp.sh`
    - `chmod`: Command to change file permissions.
    - `o`: Stands for "others," which refers to all users who are not the file owner or part of the file's group.
    - `+r`: Stands for "read" permission. It allows users to read the file’s contents.
    - `x`: Adds execute permissions. It allows users to execute the file as a program or script
    - `/tmp/xfusioncorp.sh`: The path to the script file.

    - `0`: Represents permissions for the owner (user) of the file.
    - `0`: Represents permissions for the group associated with the file.
    - `6`: Represents permissions for others (everyone else).

3. Verify the file permissions.

    `ls -lrt /tmp/xfusioncorp.sh`