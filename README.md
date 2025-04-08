# TDM-INP-TAZ-to-CensusTract

This script performs a **spatial join** between TAZ centroids and U.S. Census tracts in Utah to assign each TAZ to its corresponding **Census Tract GEOID**. The result is exported as a CSV for further geographic or demographic analysis.

## Workflow Overview

### 1. Libraries & Environment Setup
- Imports core libraries: `pandas`, `numpy`, `matplotlib`, `os`
- Uses `arcgis` Python API for spatial operations
- Sets working and results directories

### 2. Input Data
- **Tract shapefile**: `tl_2018_49_tract.shp`
- **TAZ centroids shapefile**: `TAZCentroids.shp`

### 3. Spatial Processing
- Loads shapefiles into Spatially Enabled DataFrames (`sdf`)
- Verifies and sets correct spatial reference (`EPSG:26912`)
- Performs spatial join: assigns each TAZ centroid to a Census Tract polygon

### 4. Output
- Extracts key fields: `TAZID` and matched `GEOID`
- Saves result as:  
