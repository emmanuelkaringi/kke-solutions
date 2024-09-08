# Task Definition
With the installation of new tools on the app servers within the `Stratos Datacenter`, certain functionalities now necessitate graphical user interface (GUI) access.

1. Adjust the default `runlevel` on all App servers in `Stratos Datacenter` to enable GUI booting by default. It's imperative not to initiate a server reboot after completing this task.

# Solution
1. Login or SSH into `App server 1`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Set the default target to `graphical.target`.

    `sudo systemctl set-default graphical.target`
    - This command will ensure that the system boots into the GUI mode by default when it is rebooted next time.

3. Verify the default target.

    `systemctl get-default`
    - The output should show: `graphical.target`

4. Repeat step 1 to 3 for the other two app servers.