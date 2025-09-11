# **GEE Python API Script to Trace Eruption History of Volcanic Sites Using Satellite Imagery.**



**Description:**

A custom Python script built on the Google Earth Engine (GEE) API to trace volcanic activity from historic
Sentinel-2 satellite data for a region of interest. By simply setting the site location, date range, cloud cover limit, 
and hotspot index threshold, the workflow filters images with potential thermal anomalies associated with volcanic activity.
It uses the Normalized Hotspot Index (NHI) proposed by Marchese et al. (2019), and helps visualise a timeline of 
eruption history for that site.

## Dependencies:
- earthengine-api (requires Google Earth Engine account + authentication)
- geemap
- geopandas
NOTE: If these packages are not already installed, you may need to install them.  
In Step 2, uncomment the line below to install:
"%pip install earthengine-api geemap geopandas"

## Set Input Parameters in STEP 1
1. Location –  Use AOI coordinates OR use a AOI vector file
2. Date Range & Cloud Filter – Set your preferred dates and cloud cover percentage
3. NHI Threshold – Adjust NHI Value. It ranges form -1 to 1, with values > 0 indicating potential hotspots. 
Tip: To reduce false positives, use a higher threshold value (example: 0.2) 
