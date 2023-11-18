 ## Upload files from linux(ubuntu) to smb remote storage 
 
 #### Create credentials file
 ```bash
touch ~/.credentials
nano ~/.credentials

# Add the following content to the fie and 
username=<smbUser>
password=<password>
domain=<203.159.00.00>
# Save and Exit

# Change the file permission setting for the created file,
# where read and write permission is granted to owner,
# and no permission is granted to the group and user.
sudo chmod 600 ~/.credentials 
 ```

#### Make a directory to mount the SMB network drive
```bash 
cd /mnt/smb_resource/
```
#### Mount the SMB network drive to the mountpoint created above

```bash
sudo mount -t cifs -o credentials=~/.credentials //203.159.00.00/datastore/ /mnt/smb_resource
```

#### Finally, clone the directory using `rsync` command

```bash
rsycn -avr --dry-run /source/ /mnt/smb_resource/
```
`a`: archive, to preserve symbolic links, special and device files, modification times, groups, owners and permissions. It is recommend to run this, and preserves almost everything
`r`: recursive, during directory syncing
`v`: verbose
`n or --dry-run`: rsync will only perform trial run when this is used.

`--delete`: [CAUTION!] This will delete extraneous files from the `receiving sides` which are not available in the sending side.
