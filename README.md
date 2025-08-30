Offshore Floating Solar: Viability and Contribution in Australia
This repository contains the full Python analysis pipeline for the MSc Dissertation titled "Offshore Floating Solar: Assessing Viability and Contribution in Australia". The code processes geospatial and climate data to identify and rank optimal locations for Offshore Floating Solar (OFPS) deployment around Australia.

📂 Project Structure
The repository is organized into the following directories:

data/: This directory is intended for all input data files. It should be created manually and populated according to the "Data Acquisition" section below. This folder is ignored by Git to avoid uploading large files.

src/: Contains all the Python scripts for the analysis, which are executed in sequence by main.py.

results/: All output files, including CSVs and final plots, will be saved here. This directory is created automatically when the analysis is run.

⚙️ Setup Instructions
1. Clone the Repository
Clone this repository to your local machine:

git clone <your-repository-url>
cd <repository-name>

2. Install Dependencies
This project uses Python 3. It is recommended to use a virtual environment.

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

# Install all required libraries
pip install -r requirements.txt

3. Data Acquisition
The raw data required for the analysis must be downloaded and placed in the data/ directory due to its size.

Geospatial Data
Download the following shapefiles and place them in subdirectories within data/:

Natural Earth Coastline:

File: ne_10m_coastline.zip

Source: Natural Earth 1:10m Physical Vectors

Action: Unzip and place the contents in data/ne_10m_coastline/.

Collaborative Australian Protected Areas Database (CAPAD):

File: CAPAD2020_marine.zip

Source: data.gov.au

Action: Unzip and place the contents in data/Marine_Protected_Areas/.

Australian Maritime Ports:

File: Maritime_Ports.zip

Source: Digital Atlas of Australia

Action: Unzip and place the contents in data/Major_Maritime_Ports/.

Australian Electricity Transmission Lines:

File: Electricity_Transmission_Lines.zip

Source: Digital Atlas of Australia

Action: Unzip and place the contents in data/Electricity_Transmission_Lines/.

ERA5 Climate Data
The climate data is from the ECMWF ERA5 dataset. Download the following variables as separate NetCDF (.nc) files from the Copernicus Climate Data Store (CDS).

Geographical Area: Australia (North: -9, South: -45, West: 112, East: 155)

Years: 2023 to 2024 (or your chosen analysis period)

Time: All hours

Download each of the following datasets and save them in the data/ directory with the specified filenames:

Variable(s)

Product Type

Format

Filename

2m temperature

Reanalysis

NetCDF

2m_temperature.nc

10m u-component of wind

Reanalysis

NetCDF

U_wind1.nc

10m v-component of wind

Reanalysis

NetCDF

V_wind1.nc

Mean wave period

Reanalysis

NetCDF

MeanWavePeriod.nc

Significant height of combined wind waves and swell

Reanalysis

NetCDF

SignificantWave.nc

Surface solar radiation downwards

Reanalysis

NetCDF

SurfaceSolarRadiation.nc

Maximum individual wave height

Reanalysis

NetCDF

MaximumIndividualWave.nc

Instantaneous 10m wind gust

Reanalysis

NetCDF

InstantaneousWind.nc

Water depth

Reanalysis

NetCDF

Depth.nc

Land-sea mask (for a reference grid)

Reanalysis

NetCDF

Australia.nc

▶️ Running the Analysis
Once all data is in place, you can run the entire pipeline with a single command from the root directory of the project:

python src/main.py

The script will execute each tier of the analysis in order, printing the progress to the console.

📊 Results
All outputs, including intermediate data files (.csv), final rankings, and all plots (.png), will be saved in the results/ directory. A special subfolder results/case_study_plots/ will be created for the final deep-dive analysis plots.
