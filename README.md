# OFPSTieredMethodologyCode
This code describes and executes the methodology for identifying areas with high potential for OFPS in Australia. However, this code can be utilised for other areas in the world, providing their is suitable information on marine protected areas and maritime ports.

Data Acquisition
This project requires two types of external data: geospatial shapefiles for filtering and ERA5 climate data for the energy yield analysis. Due to their size, the large climate data files are not included in this repository and must be downloaded manually.

1. Geospatial Data (Shapefiles)
These files are used for the physical and practical filtering of potential sites (Tiers 1, 2, and 4). Please download them and place them in a data/shapefiles/ directory.

Coastlines: Download the "Coastline" dataset from Natural Earth Data.

Marine Protected Areas (MPAs): Download the "Collaborative Australian Protected Areas Database (CAPAD) 2020" from the Australian Government's data repository.

Maritime Ports & Electricity Grid: Download the "Maritime Ports" and "Electricity Transmission Lines" shapefiles from the Digital Atlas of Australia.

2. Climate and Ocean Data (ERA5)
The core meteorological and oceanographic data is sourced from the ECMWF ERA5 reanalysis dataset. Follow these steps to acquire the necessary files:

Go to the Copernicus Climate Data Store (CDS). You will need to create a free account.

On the download form, select the following parameters:

Product type: Reanalysis

Variables:

2m temperature

10m u-component of wind

10m v-component of wind

Surface solar radiation downwards

Mean wave period

Significant height of combined wind waves and swell

Maximum individual wave height

Maximum instantaneous 10m wind gust

Year: 2023 and 2024

Month: All

Day: All

Time: All

Geographical area: Specify the coordinates for Australia:

North: -9

South: -44

West: 112

East: 154

Format: NetCDF

Submit the form. The request will be processed in the CDS queue, and you will be able to download the .nc file once it is ready.

Place the downloaded .nc file(s) into the data/ directory of this project before running the analysis scripts.
