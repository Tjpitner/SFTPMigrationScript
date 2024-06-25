# SFTP Migration Scripts

This repository contains scripts to assist with the migration of directories and setting appropriate permissions for an SFTP server.

## Scripts

The following scripts are used in sequence to create directories, set ownership, and apply permissions as part of the SFTP migration process.

```bash
# Replace './' with 'mkdir ' in migratedfolders.txt
sed -i 's/\.\//mkdir /g' migratedfolders.txt
```bash

# Display the contents of migratedfolders.txt
cat migratedfolders.txt 

# Execute the commands in migratedfolders.txt to create directories
. migratedfolders.txt

# Replace 'mkdir ' with 'chown "customer":"yourcompany" ' in migratedfolders.txt
sed -i 's/mkdir /chown "customer":"yourcompany" /g' migratedfolders.txt

# Display the contents of migratedfolders.txt
cat migratedfolders.txt 

# Execute the commands in migratedfolders.txt to change ownership
. migratedfolders.txt

# Replace 'chown "customer":"yourcompany" ' with 'chmod 775 ' in migratedfolders.txt
sed -i 's/chown "customer":"yourcompany" /chmod 775 /g' migratedfolders.txt

# Display the contents of migratedfolders.txt
cat migratedfolders.txt 

# Execute the commands in migratedfolders.txt to set permissions
. migratedfolders.txt

# Find and list all directories in the current directory
find . -type d 

# Remove migratedfolders.txt file
rm migratedfolders.txt 

# Change ownership of specific directories to root:root
chown root:root files logs tmp

