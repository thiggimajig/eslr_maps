# eslr_maps
Scripts to make ESLR maps of your country of choice

## Pre-requisites:
Create a virtual environment from the requirements.txt file
Have the bounding box coordinates for the country you want to map http://bboxfinder.com/#0.000000,0.000000,0.000000,0.000000 <br>
eslr point JRC data - JRC https://data.jrc.ec.europa.eu/dataset/jrc-liscoast-10012#dataaccess <br>
hydrosheds data - hydrosheds https://www.hydrosheds.org/products/hydrobasins <br>
country boundary shapefile - NE https://www.naturalearthdata.com/downloads/10m-cultural-vectors/ <br> 

## Step 1: Pull and merge the raster elevation data with script earthexplorer_italy_data_pull.ipynb
<b>Input</b> - bounding box coordinates <br>
<b>Output</b> - merged tif file <br>

## Step 2: In QGIS follow steps 1-15 in this file https://docs.google.com/document/d/1bqEfdx70kfs_gK417adjjxi2oWqjoyGR/edit 
<b>Input</b> - merged tif file <br>
<b>Output</b> - shapefile with zonal statistics on the elevation and hydrobasin id; a csv file with the nearest 5 eslr points on watershed id for each projection (so 4 csv file total)

## Step 3: Clean the data for the vulnerability maps in "prep_for_transform_map.ipynb" 
<b>Input</b> - shapefile with zonal statistics on the elevation and hydrobasin id; 4 csv files (by projection) with the nearest 5 eslr points on watershed id for each projection <br>
<b>Output</b> - shapefile with subtractions <br>

## Step 4: Create the 12 vulnerability maps and 36 shapefiles 
<b>Input</b>- shapefile with subtractions <br>
<b>Output</b> - 12 maps by vulnerability, along with the 36 unmerged shapefiles so that anyone can work on removing isolates <br> 

 
## Other Resources:
Blog Post https://dev.to/thiggimajig/plan-to-analyze-sardinias-vulnerability-to-sea-level-rise-in-2050-3jmp
Blog Post After Feedback https://dev.to/thiggimajig/analyzing-italys-vulnerability-to-sea-level-after-applying-feedback-4nb8
