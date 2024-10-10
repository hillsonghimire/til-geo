## (on linux)

#### Create python environment: - [my material for mamba🐍](python/osgeo-mamba.md)

#### Install GEE API 🌍
Before using the Earth Engine API or earthengine command line tool, you must perform a one-time authentication that authorizes access to Earth Engine on behalf of your Google account. 

On `conda/mamba` - GEE API Installation
```bash
mamba install -c conda-forge earthengine-api
```
#### Get Credentials 🔒

```bash
earthengine authenticate
```

#### Credentials location 📁
```bash
ls $HOME/.config/earthengine/credentials
```

#### To check if the credentials are working or not ✅
```bash
ee.Authenticate()
ee.Initialize(project='my-project')
```

#### Verify by printing metadata for a DEM dataset ☑️
print(ee.Image('USGS/SRTMGL1_003').getInfo())


#### Updating API 🆕
```bash
mamba update -c conda-forge earthengine-api
```

Note: After seting up the python API for google earth engine, `earthengine` command on bash will not give any error


Reference: 
Installation Guide: https://developers.google.com/earth-engine/guides/python_install-conda
To learn more on GEE CLI: https://developers.google.com/earth-engine/guides/command_line