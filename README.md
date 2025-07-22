# **Detecting Volcanic Activity in Sentinel-2 Imagery Using a Custom Google Earth Engine Python API script**



**Description:**

This custom Python script built using the Google Earth Engine (GEE) API  detects volcanic activity from Sentinel-2 imagery in user-defined areas and timeframes. By setting three key parameters i.e. (i) location, (ii) Date range, and (iii) NHI threshold, the script automates the processing and filtering of Sentinel-2 data. 

It applies the Normalized Hotspot Index (NHI) to SWIR and NIR bands (B12, B11, B8A), based on the method proposed by Marchese et al. (2019), to identify thermal anomalies associated with volcanic activity. The script was run for several volcanic sites in Iceland (2020–2024) and the results include a detailed ArcGIS StoryMap highlighting time-series visualization of key eruption zones showcasing spatial patterns and impacts.



**Data processing and filters used in the script include:**

i) Loading Sentinel-2 Level 1C dataset (Top-of-atmosphere reflectances).

ii) Clipping dataset to Area of Interest (AOI).

iii) Attaching acquisition dates to each image.

iv) Converting reflectance to radiance for bands of interest (Because thermal sensors measure emitted energy, not reflected sunlight).

v) Calculating and Adding NHI index Bands.

vi) Filtering scenes with Maximum B12 Radiance > 2 (Discriminates volcanic activity from cooler surfaces \& Reduces false positives.

vii) Filtering scenes using a threshold NHI value (e.g., 0.2) (To minimize false positives).



**# Dependencies:**

\- earthengine-api (requires Google Earth Engine account + authentication)

\- geemap

\- geopandas

\- math (built-in)

pip install earthengine-api geemap geopandas

\# NOTE: Authenticate GEE using: earthengine authenticate (Step 1)



**# Guide for Setting Custom Input Parameters in the script:**

1\. Location

– Use a vector polygon file in Step 3, or manually enter coordinates in Step 4.



2\. Date Range \& Cloud Filter

– Set your preferred dates and cloud cover in Step 5.



3\. NHI Threshold

– Adjust the hotspot filter value in Step 13. – The NHI index ranges form -1 to 1 and highlights potential hotspots (values > 0).

To reduce false positives, use a higher threshold like 0.2 in Step 13. 



**References:**

Marchese, F., Genzano, N., Neri, M., Falconieri, A., Mazzeo, G. and Pergola, N., 2019. A multi-channel algorithm for mapping volcanic thermal anomalies by means of Sentinel-2 MSI and Landsat-8 OLI data. *Remote Sensing, 11*(23), p.2876.

