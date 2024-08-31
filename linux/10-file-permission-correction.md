# Task Description
After conducting a security audit within the `Stratos DC`, the Nautilus security team discovered misconfigured permissions on critical files. To address this, corrective actions are being taken by the production support team. Specifically, the file named `/etc/hostname` on `Nautilus App 1` server requires adjustments to its `Access Control Lists (ACLs)` as follows:

1. The file's user owner and group owner should be set to `root`.

2. `Others` should possess `read only` permissions on the file.

3. User `mariyam` must not have any permissions on the file.

4. User `jerome` should be granted read only permission on the file.

# Solution
1. Login or SSH into `App server 1`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Set the user owner and group owner to `root`.

    `sudo chown root:root /etc/hostname`
    - `chown`: Stands for "change owner". Command used to change the ownership of files and directories.
    - `root:root`: Specifies the new owner and group owner of the file. The first root is the user owner, and the second root is the group owner.
    - `/etc/hostname`: The path to the file whose ownership is being changed.

3. Set permissions for `Others` to `Read-Only`.

    `sudo chmod o=r /etc/hostname`
    - `chmod`: Stands for "change mode". Command used to change the permissions of files or directories.
    - `o=r`: Specifies the permissions for "others" (all users who are not the file owner or members of the file's group). `o` stands for "others", and `r` grants read permission. The `=` ensures that read is the only permission given, removing any other permissions.

4. Remove all permissions for user `mariyam`.

    `sudo setfacl -m u:mariyam:0 /etc/hostname`
    - `setfacl`: Stands for "set file access control list". It is used to modify the access control lists (ACLs) of a file or directory.
    - `-m`: Stands for "modify". It indicates that you want to modify the existing ACLs for the file.
    - `u:mariyam:0`: Specifies the ACL entry to modify. `u` stands for "user", `mariyam` is the username, and `0` means "no permissions" (neither read, write, nor execute).

5. Grant `read only` permission to user `jerome`.

    `sudo setfacl -m u:jerome:r /etc/hostname`
    - `r` : Grants read-only permission.