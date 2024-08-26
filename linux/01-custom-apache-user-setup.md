# Task Description

In response to heightened security concerns, the `xFusionCorp Industries` security team has opted for custom Apache users for their web applications. Each user is tailored specifically for an application, enhancing security measures. Your task is to create a custom Apache user according to the outlined specifications:

a. Create a user named `kareem` on `App server 3` within the Stratos Datacenter.

b. Assign a unique UID `1045` and designate the home directory as `/var/www/kareem`.

# Solution
1. Login or SSH into `App server 3`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create user `kareem`.

    `sudo useradd -m kareem`

3. Verify user creation.

    `id kareem`

4. Modify the user `kareem` with a unique UID and home directory.

    `sudo usermod -u 1045 -d /var/www/kareem -m kareem`
    
    - `u 1045` - sets/Specifies the UID to 1045.
    - `d /var/www/kareem` - Specifies the home directory for the user `/var/www/kareem`.
    - `m` - Creates the home directory if it does not already exist.
5. Verify directory.

    `grep kareem /etc/passwd`

Alternatively, `sudo useradd -u 1045 -d /var/www/kareem -m kareem` can be used to achieve the above task in one go.