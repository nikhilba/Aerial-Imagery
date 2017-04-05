# Aerial-Imagery
Authors: [Nikhil Binod Agarwal](https://github.com/nikhilba) and [Tina Hong Bu](https://github.com/TinaHongBu), Carnegie Mellon University, under the guidance of [Prof. Zico Kolter](http://zicokolter.com/)

# Status
This ongoing project is expected to be completed by the end of April 2017.

# Required Package
So far, following packages have been used to run the code in this repo:
 - geopandas
 - shapely
 - fiona
 - matplotlib
 - seaborn
 - pandas

Code is contained in the Code/ directory (iPython Notebooks) and Data (except Satellite Images) is contained in the Dataset/ directory

# Problem Statement
We are interested in applying the machine learning techniques to to satellite images of a location (in our case, we look at Pittsburgh city) and related census information (such as income, age, sex, race, etc.). We attempt to investigate the possibility of predicting poverty in a region.

Gathering census information is expensive and resource intensive. Our analysis would be a cost effective alternative solution using a fairly high-resolution aerial imagery to obtain an approximation of the census information at a significatly reduced cost. This can be achieved by building a classifier that can predict income level of a regoin.

# Data Collection & Processing
To generate the desired predictor training data, we have downloaded the satellite images of Pittsburgh using [Google Static Maps Api](https://developers.google.com/maps/documentation/static-maps/) and Census data by Block group from [US Census Bureau](https://www.census.gov/geo/maps-data/data/tiger-data.html). We then mapped each satellite image with its corresponding income level info.

We were able to create a unique dataset from scratch using the open source infomation that is available online.

...
