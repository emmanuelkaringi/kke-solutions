# Task Description

As part of the temporary assignment to the Nautilus project, a developer named `rose` requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:

a. Create a user named `rose` on `App Server 3` in Stratos Datacenter. Set the expiry date to `2024-02-17`, ensuring the user is created in lowercase as per standard protocol.

# Solution
1. Login or SSH into `App server 3`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create the user with the specified expiry date.

    `sudo useradd -e 2024-02-17 rose`

    - `-e 2024-02-17` - sets the expiry date for the user account to February 17, 2024.

3. Verify that the user has been created with the correct expiry date.

    `sudo chage -l rose`