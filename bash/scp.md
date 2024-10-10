## SCP file transfer cheatsheet

#### Securely copy a file from a local machine to a remote machine in Linux
Note: use `scp -r` to copy entire directory and its content recursively.
```bash
scp ./transferring_file_name  remoteuser@remotehost:/remote/directory
```


#### Securely copy a file from remote machine to our local machine.
(Note: use `scp -r` to copy entire directory and its content recursively.)
```bash
scp user@remotehost:/home/user/remote_file_name ./local_folder
```

#### Preserving original file metadata during transfer
```bash
scp -p source_file user@hostname:destination_file
```
