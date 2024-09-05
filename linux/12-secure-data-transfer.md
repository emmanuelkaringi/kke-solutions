# Task Description
A `Nautilus` developer has stored confidential data on the jump host within `Stratos DC`. To ensure security and compliance, this data must be transferred to one of the app servers. Given developers lack direct access to these servers, the system admin team has been enlisted for assistance.

1. Copy `/tmp/nautilus.txt.gpg` file from `jump server` to `App Server 1` placing it in the directory `/home/code`.

# Solution
1. Copy `/tmp/nautilus.txt.gpg` file from `jump server` to `App Server 1` placing it in the directory `/home/code`.

    `scp /tmp/nautilus.txt.gpg tony@ipaddress:/home/code/`
    - `scp`: Used for secure copy (SCP) over SSH. It allows one to transfer files between different hosts.
    - `/tmp/nautilus.txt.gpg`: The path to the file on the jump server that will be copied.
    - `tony@ipaddress`: The SSH credentials (`username@ip_adress`) to access `App Server 1`. Replace `ipadress` with the hostname or IP address of `App Server 1`.
    - `:/home/code/`: The destination path on App Server 1 where the file will be copied.

2. Verify that the file was copied to `App server 1`:
    - Login/SSH into App server 1 - `ssh user@ip-address/hostname`
    - CD into `/home/code` (`cd /home/code`) and list (`ls`)to see the files in that directory.