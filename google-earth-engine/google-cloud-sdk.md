## (on linux)

For updated instructions: https://cloud.google.com/sdk/docs/install#linux

This is more generic to linux, and there are different ways to do this more directly on ubuntu and RHLE.

#### Check Python version
`python3 --version`

#### Download Google Cloud CLI
`curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-linux-x86_64.tar.gz`

#### Extract the archive
`tar -xf google-cloud-cli-linux-x86_64.tar.gz`

#### Run installation
`./google-cloud-sdk/install.sh`

#### Initialize gcloud
`./google-cloud-sdk/bin/gcloud init`


Instead of always trying to provide the full path of `gcloud`, it can be set to run when `gcloud` is called setting the `path variable` :
```
echo "export PATH=\$PATH:$HOME/google-cloud-sdk/bin" >> ~/.bashrc
source ~/.bashrc
```

