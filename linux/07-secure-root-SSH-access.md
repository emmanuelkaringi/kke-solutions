# Task Description
Following security audits, the `xFusionCorp Industries` security team has rolled out new protocols, including the restriction of direct root SSH login.

a. Your task is to disable direct SSH root login on all app servers within the `Stratos Datacenter`.

# Solution
1. Login or SSH into `App server 1`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Modify the `PermitRootLogin` line in `/etc/ssh/sshd_config` file.

    `sudo sed -i "s/^PermitRootLogin.*/PermitRootLogin no/" /etc/ssh/sshd_config`

3. Restart the SSH service to apply changes.

    `sudo systemctl restart sshd`

4. Verify that direct SSH root login has been successfully disabled.

    `sudo grep -i "^PermitRootLogin" /etc/ssh/sshd_config`

    - This command will search for the `PermitRootLogin` line in the `/etc/ssh/sshd_config` file.
    - If the output is `PermitRootLogin no`, then direct root login has been disabled.

5. Repeat from `step 1` for `App server 2` and `App server 3`.