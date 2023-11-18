## To download data from dataspace

#### On `python environment` - install `s3cmd` package
```bash
!pip install s3cmd==2.3.0
```
#### Create a configuration file to download Sentinel-1 data from S3
Setup [copernicus dataspace](https://dataspace.copernicus.eu/) account.
The `s3 credentials` can be setups from the link: 
https://eodata-s3keysmanager.dataspace.copernicus.eu/panel/s3-credentials.
This configuration detail can be used to create configurations as below:

```bash
nano ~/.s3cfg

# Add following configuration to the file
# _____________________________________________
# [default]
# access_key = <access_key>
# host_base = eodata.dataspace.copernicus.eu
# host_bucket = eodata.dataspace.copernicus.eu
# human_readable_sizes = False
# secret_key = <secret_key>
# use_https = true
# check_ssl_certificate = true
# _____________________________________________
```

#### Test if the installation and configuration works or not
```bash
s3cmd -c ~/.s3cfg ls
```


#### The name of the file can be grabbed from the dataspace portal. Use the product name to download the file as follows:
```bash
## Downloading File
s3cmd -c s3cfg.txt get s3://eodata/Sentinel-1/SAR/IW_SLC__1S/2023/11/02/S1A_IW_SLC__1SDV_20231102T184336_20231102T184410_051042_062795_7245.SAFE/measurement/s1a-iw1-slc-vh-20231102t184338-20231102t184408-051042-062795-001.tiff --skip-existing

# # Downloading, if the data are already archive, we use -r flag for recursive downloading
s3cmd -c ~/.s3cfg -r get s3://eodata/Sentinel-1/SAR/SLC/2019/10/13/S1B_IW_SLC__1SDV_20191013T155948_20191013T160015_018459_022C6B_13A2.SAFE/ --skip-existing
```
`--skip-existing` flag is used to do checksum and skip the files that has already exists in the download directory. This is very useful in slow internet connection or if the download size is large with possibility of failing. When restarting the download the command skips the existing files.