# Task Description
Within the Stratos DC, the backup server holds template XML files crucial for the Nautilus application. Before utilization, these files require valid data insertion. As part of routine maintenance, system admins at `xFusionCorp Industries` employ string and file manipulation commands.

1. Your task is to substitute all occurrences of the `string` Text with `Cloud` within the XML file located at `/root/nautilus.xml` on the backup server.

# Solution
1. Login or SSH into `Nautilus Backup Server`. The users, ip addresses and passwords are provided in the documentation.

    `ssh user@ip-address/hostname`

2. View the content of the file `/root/nautilus.xml`.

    `sudo cat /root/nautilus.xml`

3. Search for and list all occurrences of the word `Text` in the file.

    `grep -n "Text" /root/nautilus.xml`

4. Substitute all occurrences of the string `Text` with `Cloud` within the XML file `/root/nautilus.xml`.

    `sudo sed -i 's/Text/Cloud/g' /root/nautilus.xml`
    - `sed`: Command used for searching, finding, and replacing text.
    - `-i`: Tells sed to edit the file in place, meaning the changes will be directly applied to the file without creating a backup.
    - `s`: Stands for substitution.
    - `Text`: The string you want to find.
    - `Cloud`: The string you want to replace "Text" with.
    - `g`: Stands for "global", meaning all occurrences of "Text" within each line will be replaced, not just the first one.

5. Verify that the substitution was successful.

    - `grep -n "Text" /root/nautilus.xml` - This should not return anything if th substitution was successful.

    - `grep -n "Cloud" /root/nautilus.xml` - This should return results similar to what was generated in step 3 but with the word `Text` replaced with `Cloud`.