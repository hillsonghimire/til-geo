## Installation of Google Cloud CLI

#### Download google-cloud package
On `Ubuntu`: Get latest URL from : https://cloud.google.com/sdk/docs/install#linux
```bash
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-464.0.0-linux-x86_64.tar.gz
```
#### unzip

```bash
tar -xf google-cloud-cli-464.0.0-linux-x86_64.tar.gz
```

#### add CLI to path

```bash
./google-cloud-sdk/install.sh
```

#### to initialize the gcloud CLI, run `gcloud init`
```bash
./google-cloud-sdk/bin/gcloud init
```
After this step, a link will appear that will redirect to authenticate, and after that step you'll be prompted to select the google cloud project form the list.

#### To access the `google cloud storage bucket`, we need to install `gsutil`, it comes bundled with `google-cloud-cli`
```bash
sudo apt-get update && sudo apt-get install google-cloud-cli
# For details: https://cloud.google.com/storage/docs/gsutil_install#deb
```

## happppy in cloud !!!! :)