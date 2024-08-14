# PySCHISM-Test_Hercules
This is a test directory regarding the setup and installation of PySCHISM in MSU Hercules cluster

## PySCHISM Installation on NOAA Hercules Cluster

### Summary
Successfully installed PySCHISM on the NOAA Hercules cluster after resolving dependency issues. This guide outlines the steps taken to achieve a working installation.

### Environment
- Cluster: Hercules
- Python version: 3.9.18 (conda-forge)

### Installation Steps
1. Create and activate a new conda environment:
   ```bash
   conda create -n pyschism_env python=3.9
   conda activate pyschism_env

2. Install UDUNITS-2 library::
   ```bash
   conda install -c conda-forge udunits2

3. Install key dependencies::
   ```bash
   conda install -c conda-forge gdal sqlite fiona

4. Install additional required packages::
   ```bash
   conda install -c conda-forge numpy scipy netcdf4 matplotlib geopandas shapely

5. Install PySCHISM::
   ```bash
   pip install pyschism

**Key Observations**

- Using the conda-forge channel was crucial for compatibility.
- Installing UDUNITS-2 resolved initial cfunits-related errors.
- Updating GDAL and related libraries (sqlite, fiona) solved symbol errors.
- Installing major dependencies via conda before using pip for PySCHISM ensured compatibility.


**Notes**

- A warning about the deprecated seawater library appears but does not affect functionality:
_UserWarning: The seawater library is deprecated! Please use gsw instead._
