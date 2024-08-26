# Task Description
The system admin team at `xFusionCorp Industries` has streamlined access management by implementing group-based access control. Here's what you need to do:

a. Create a group named `nautilus_admin_users` across all `App servers` within the Stratos Datacenter.

b. Add the user `stark` into the `nautilus_admin_users` group on all App servers. If the user doesn't exist, create it as well.

# Solution
1. Login or SSH into `App server 1`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create user `stark`, create group `nautilus_admin_users`, add user `stark` into the created group.

    `sudo useradd -m stark; sudo groupadd nautilus_admin_users; sudo usermod -aG nautilus_admin_users stark`

3. Verify user and group.

    `id stark`

    `groups stark`

4. Repeat from `step 1` for `App server 2` and `App server 3`.