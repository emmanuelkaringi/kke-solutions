# Task Description
Within the Stratos DC, the Nautilus storage server hosts a directory named `/data`, serving as a repository for various developers non-confidential data. Developer `siva` has requested a copy of their data stored in `/data/siva`. The System Admin team has provided the following steps to fulfill this request:

a. Create a compressed archive named `siva.tar.gz` of the `/data/siva` directory.

b. Transfer the archive to the `/home` directory on the Storage Server.

# Solution
1. Login or SSH into `storage server`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. Create a compressed archive named `siva.tar.gz` of the `/data/siva` directory.

    `tar -czf siva.tar.gz /data/siva`
    - `tar`: Is used to create and manipulate archive files.
    - `-c`: Stands for "create" a new archive.
    - `z`: Compresses the archive using gzip.
    - `f`: Specifies the name of the archive file (siva.tar.gz).
    - `siva.tar.gz`: The name of the output compressed archive file.
    - `/data/siva`: The directory to be archived and compressed.

3. Transfer the `siva.tar.gz` archive to the `/home directory`

    `sudo mv siva.tar.gz /home/`
    - `mv`: Is used to move files or directories.
    - `siva.tar.gz`: The name of the archive file to be moved.
    - `/home/`: The destination directory for the archive.

4. Verify that the archive file was moved.

    `ls /home/`