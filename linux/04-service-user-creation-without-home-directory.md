# Task Description
In response to the latest tool implementation at `xFusionCorp Industries`, the system admins require the creation of a service user account. Here are the specifics:

a. Create a user named `rose` in `App Server 1` without a home directory.

# Solution

1. Login or SSH into `App server 1`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create the user `rose` without a home directory.

    `sudo useradd -M rose`

    - `-M`: Prevents the creation of a home directory for the user.