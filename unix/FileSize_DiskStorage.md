## Check the storage filesystem and file/folder sizes

#### On `LINUX`, to display all block devices (except RAM) in a tree-like format
```bash
lsblk
```


#### On `LINUX`, to display amount of disk space available on the filesystem with each file name's argument
```bash
df
```
Additionally, to include dummy file systems `-a` flag can be used
`-H` flag is used to display in human readable format
```bash
df -laH

# To sort the result
df -lH |  sort -h

# With only the desired output columns
df -H --output=size,used,avail
```

## At any directory, to check the file sizes (most useful**)
`-h` flag is used to display resut in human readable format, and --max-depth
```bash
du -h --max-depth=1

# Additionally the location of the trash file in linux
>> /home/<user>/.local/share/Trash
```


To see all the files with human readable size, along with sorting parameters
```bash
du -lah --max-depth=1 . |  sort -h
```
`-a` or `--all` flag is used to write counts for all files, not just directory.
`-l` or `--count-links` is used to count sizes many times if hard linked.