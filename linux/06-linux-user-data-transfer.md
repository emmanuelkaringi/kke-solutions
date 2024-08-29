# Task Description
Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus `App Server 2` at the `/home/usersdata` location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:

a. Locate all files (excluding directories) owned by user `john` within the `/home/usersdata` directory on `App Server 2`. Copy these files while preserving the directory structure to the `/official` directory.

# Solution
1. Login or SSH into `App server 2`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Locate all files (excluding directories) owned by user `john` within the `/home/usersdata` directory.

    `find /home/usersdata -type f -user john`

3. Copy the files owned by `john` while preserving the directory structure to the `/official` directory.

    `find /home/usersdata -type f -user john -exec cp --parents {} /official \;`

    - `find /home/usersdata`: Start searching from the `/home/usersdata directory`.
    - `-type f`: Only find files (exclude directories).
    - `-user john`: Only find files owned by the user john.
    - `-exec cp --parents {} /official \;`: For each file found, execute the cp command with the `--parents` option. This option ensures that the original directory structure is preserved when copying to the `/official` directory.
    - `{}` is a placeholder for each file found by find.
    - `\;` marks the end of the `-exec` command.

**Altelnatively, you can run `find /home/usersdata -type f -user john -print0 | xargs -0 -I {} cp --parents {} /official` to achieve step 1 and 2 in one command.**

- `-print0`: Output the full file paths separated by a null character (\0). This is safer for file names containing spaces or special characters.
- `xargs -0 -I {} cp --parents {} /official`:
    - `-0`: Tells xargs to expect input items separated by a null character (\0), ensuring file names with spaces or special characters are handled correctly.
    - `-I {}`: Placeholder for each input item from find. Replaces `{}` with each file path found.