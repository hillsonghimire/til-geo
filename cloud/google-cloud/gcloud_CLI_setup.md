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

## happppy in cloud !!!! :)