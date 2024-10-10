## to mount and unmount drive

#### Create credentials file
```bash
touch ~/.credentials
nano ~/.credentials

# Add the following content to the fie and 
username=<smbUser>
password=<password>
domain=<203.159.XX.XX>

# Save and Exit

# Change the file permission setting for the created file,
# where read and write permission is granted to owner,
# and no permission is granted to the group and user.
sudo chmod 600 ~/.credentials 

```

#### Mount the `smb` resource to the mountpoint
```
sudo mount -t cifs -o credentials=~/.credentials '//203.159.XX.XX/datastore/' /mnt/mountpoint
```

#### To unmount
```
sudo umount /mnt/mountpoint
```