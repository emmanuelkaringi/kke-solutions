# Task Description
To accommodate the backup agent tool's specifications, the system admin team at `xFusionCorp Industries` requires the creation of a user with a non-interactive shell. Here's your task:

a. Create a user named `mark` with a non-interactive shell on `App Server 2`.

# Solution
1. Login or SSH into `App server 2`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create user `mark` with a Non-Interactive Shell.

    `sudo useradd -s /sbin/nologin mark`

    OR
    
    `sudo useradd -s /bin/false mark`

3. Verify user creation and shell.

    `grep mark /etc/passwd`