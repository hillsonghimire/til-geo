## Downloading Public Dataset from AWS s3 bucket

#### Installation of AWS CLI

On `Ubuntu`
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```
#### List data directory or recursive directories

```bash
# for immediate directory
aws s3 ls --no-sign-request s3://maxar-opendata/

# for recursive directories
aws s3 ls --no-sign-request s3://maxar-opendata/ --recursive

# note: '--no-sign-request' flag: to access data that doesn't require authentications
```

#### Clone the directory to local folder recursively (not preferred)

```bash
aws s3 cp --no-sign-request s3://maxar-opendata/events/ Nepal-Earthquake-Nov-2023/ /home/hillson-path/MaxarImageries/ --recursive
```

#### Sync the directory to local directory
Similar to the `rsync` command in `linux`, aws makes use of `sync` to compare and download only file that does not exist locally.

This is particularly important when copying very large repository.

```bash
aws s3 sync --no-sign-request s3://maxar-opendata/events/ Nepal-Earthquake-Nov-2023/ /home/hillson-path/MaxarImageries/
```
Note: the data integrity check is also done during the `sync` process [(stackoverflow)](https://serverfault.com/a/999393)

##### This doesn't cover
* Authentications to connect to the aws s3 bucket