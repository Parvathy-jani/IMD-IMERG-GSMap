# IMD-IMERG-GSMap

Rainfall Data Visualization

This Python script visualizes rainfall data from three sources: IMERG, IMD, and GSMAP. The script produces a six-panel plot that includes both scatter and contour maps, categorized by rain event types and spatial distribution of rainfall over the North East region of India.
Prerequisites
Software Requirements

    Python 3.8 or higher
    Required libraries:
        matplotlib
        cartopy
        pandas
        xarray
        numpy

Input Data

    IMERG Data:
        NetCDF files stored in /home/pc/Desktop/New Folder/Accumulated rain data/2022/
        Example format: IMERG_precipitation_2022.nc4
        Data contains precipitation values with time, latitude, and longitude dimensions.

    IMD Data:
        NetCDF file located at /home/pc/Desktop/IMD_Data/RF25_ind2022_rfp25.nc
        Contains daily rainfall accumulation for 2022 over India.

    GSMAP Data:
        CSV file: /home/pc/Desktop/GSMAP_data/2022/accumulated_rainfall_2022_categories.csv
        Contains latitude, longitude, and rainfall values.

    Rainfall Data (IMERG Filtered):
        CSV file: rainfall_data_2022.csv
        Contains latitude, longitude, and accumulated precipitation over a selected region.

Features of the Script
1. Rain Event Categorization

Rainfall values are classified into categories:

    Background Rain: 0–7.8 mm
    Moderate Rain Events: 7.8–39.4 mm
    Intense Rain Events: 39.4–136.6 mm
    Extreme Rain Events: ≥136.6 mm

2. Visualization Layout

The script creates a 2x3 grid of subplots with the following layout:

    Row 1 (Scatter plots):
        IMERG: Categorized rain events
        IMD: Categorized rain events
        GSMAP: Categorized rain events
    Row 2 (Contour plots):
        IMERG: Spatial distribution of rainfall
        IMD: Spatial distribution of rainfall
        GSMAP: Spatial distribution of rainfall

3. Map Setup

Each plot includes:

    Coastlines, borders, and state boundaries
    Proper geographical orientation for the North East region of India
    Tick marks and labels in degrees latitude/longitude, styled in bold

4. Legend

Rainfall categories are color-coded and shown in two-line legends positioned above the plots.
5. Color Bar

A horizontal color bar represents the rainfall range for contour plots, with levels corresponding to the rainfall categories.
How to Use

    Prepare the Data
        Ensure all data files are correctly placed in the specified directories.
        IMERG and IMD data should be in NetCDF format; GSMAP data in CSV format.

    Install Dependencies Install required Python libraries:

pip install matplotlib cartopy pandas xarray numpy

Run the Script Execute the script in your Python environment:

    python rainfall_visualization.py

    Output
        The script generates a plot saved to the working directory or displayed interactively depending on your Python environment.
        It visualizes rain events and accumulated rainfall spatial distribution.

Outputs Explained
Scatter Plots

    Show rainfall categories over the North East region of India.
    Points are colored and sized according to rainfall intensity.

Contour Plots

    Show spatial distribution of accumulated rainfall.
    Color bar at the bottom helps interpret rainfall intensity.

Customization Options

    Rainfall Categories
        Modify the categories list to adjust rainfall ranges, colors, and marker sizes.

    Region
        Change the geographical bounds for the North East region in setup_map:

        ax.set_xlim(85, 100)
        ax.set_ylim(18.5, 32)

    Map Features
        Add or remove map features (e.g., coastlines, borders) by modifying the setup_map function.

    Color Levels
        Adjust the levels and colors lists for contour plots to match desired rainfall ranges.

Limitations

    The script is region-specific to the North East region of India. Other regions require changes in geographical bounds.
    Ensure data integrity; mismatched dimensions or missing data can cause errors.

Author

Developed by a Research Assistant in Atmospheric and Climate Science to analyze and visualize rainfall data from multiple datasets.
