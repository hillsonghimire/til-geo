## (on linux)

#### Create python environment: - [material for mamba](python/osgeo-mamba.md)

#### Install GEE API
Before using the Earth Engine API or earthengine command line tool, you must perform a one-time authentication that authorizes access to Earth Engine on behalf of your Google account. 

On `conda/mamba` - GEE API Installation
```bash
mamba install -c conda-forge earthengine-api
```
#### Get Credentials

```bash
earthengine authenticate
```

#### Credentials location
```bash
ls $HOME/.config/earthengine/credentials
```