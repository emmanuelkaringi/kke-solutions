# Task Description
In alignment with security compliance standards, the Nautilus project team has opted to impose restrictions on crontab access. Specifically, only designated users will be permitted to create or update cron jobs.

1. Configure crontab access on `App Server 3` as follows: Allow crontab access to `kareem` user while denying access to the `rod` user.

# Solution
1. Login or SSH into `App server 3`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create the `/etc/cron.allow` file - This file explicitly lists the users who are allowed to use `crontab`.

    `sudo touch /etc/cron.allow`

3. Add the user `kareem` to the file created.

    `echo "kareem" | sudo tee -a /etc/cron.allow`

4. Verify the contents to ensure the user has been added.
    
    `cat /etc/cron.allow`

5. Create the `/etc/cron.deny` file - This file explicitly lists the users who are not allowed to use `crontab`.

    `sudo touch /etc/cron.deny`

6. Add the user `rod` to the file created.

    `echo "rod" | sudo tee -a /etc/cron.allow`

7. Verify the contents to ensure the user has been added.
    
    `cat /etc/cron.deny`