##### Landsat Collection 1 vs Collection 2
Collection 2 has improved data quality in comparison to collection 1, as it has improvements to the absolute geolocation accuracy, but also including updated digital elevation modelling sources, improved radiometric calibration, and enhanced quality assessment bands, in addition to updated metadata and file formats.

##### Landsat Level 1 vs Level 2
Level-2 is atmospherically corrected (Surface Reflectance) data, whereas, Level-1 contains a scaled Digital Number (DN) ( usually 8 or 16 bit unsigned integers). Level-2 is the "ready to use data" as you do not have to implement any corrections.

Additional details: https://d9-wret.s3.us-west-2.amazonaws.com/assets/palladium/production/s3fs-public/atoms/files/Landsat-C1vsC2-2021-0430-LMWS.pdf

##### Landsat Tier 1 vs Tier 2
Tier 1 data have the highest radiometric and positional quality.  They have precision terrain processing and have been inter-calibrated across the Landsat sensors.  The USGS recommends using Tier 1 data for all future time-series analysis.

Tier 2 data are still very good images.  They may have more cloud cover, affecting the radiometric calibration and obscuring ground control points within the scenes.

##### <i> Best sequence/corrected sequence: Landsat Collection 2 Level 2 Tier 1 </i>


#### Landsat data in Google Earth Engine Catalogue alos has collection of `Surface Reflectance` and `Top of Atmosphere`
The Surface Reflectance product measure the fraction of incoming solar radiation reflected from Earth's surface to the landsat sensor.
