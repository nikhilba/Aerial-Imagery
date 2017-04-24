# Aerial-Imagery
Authors: [Nikhil Binod Agarwal](https://github.com/nikhilba) and [Tina Hong Bu](https://github.com/TinaHongBu), under the guidance of [Prof. Zico Kolter](http://zicokolter.com/), Carnegie Mellon University.

# Status
This ongoing project is expected to be completed by the end of April 2017.

Code is contained in the Code/ directory (iPython Notebooks) and Data (except Satellite Images) is contained in the Dataset/ directory.
 1. Downloading Satellite Images [COMPLETED] - Code/ImageDownload.ipynb
 2. Mapping Income info with Satellite Image [COMPLETED] - Code/Read_Census_Info_BG.ipynb
 3. Classifying Images [In Progress] - Code/Aerial_Imagery_Deep_Learning.ipynb

# Required Package
So far, following packages have been used to run the code in this repo:
 - geopandas
 - shapely
 - fiona
 - matplotlib
 - seaborn
 - pandas

Deep Learning Packages:
 - Keras
 - Theano (backend)
 - Tensorflow (backend)
 
# Problem Statement
We are interested in applying the deep learning techniques to the satellite images of a location (in our case, we look at Pittsburgh city) and related census information (such as income, age, sex, race, etc.). We attempt to investigate the possibility of predicting poverty in a region.

Gathering census information is expensive and resource intensive. Our analysis would be a cost effective alternative solution using a fairly high-resolution aerial imagery to obtain an approximation of the census information at a significatly reduced cost. This can be achieved by building a classifier that can predict income level of a regoin.

# Approach
Our aim is to implement an end-to-end data science pipeine from scratch. Thus,  we create a unique dataset of Satellite Images and associate every image with its corresponding census information (in this case income). 

To be able to predict poverty using aerial images, we use deep-learning technique to generate image features and then train a classifier to predict the income level of the image. For ML model, we use neural network, specifically convolutional neural network. Tuning and training a new neural network takes a significant amount of time and effort, we thus use a [VGG-16 network model](https://gist.github.com/baraldilorenzo/07d7802847aaad0a35d3)  with weights pre-trained on ImageNet, to generate the image features. 

Such pre-trained very deep convolutional neural networks have been known to generalize well and achieve state-of-the-art results. Tweaking the last few layers of this model, we would measure its performance.

# Data Collection & Processing
We create a unique dataset from scratch using the open source infomation of the state Pennsylvania. 
 1. To generate the desired predictor training data, we first download the satellite images of Pittsburgh using [Google Static Maps Api](https://developers.google.com/maps/documentation/static-maps/)
 2. The Census data by Block group is downloaded from the [US Census Bureau](https://www.census.gov/geo/maps-data/data/tiger-data.html).
 3. We then map each satellite image with its corresponding income level info. 
 4. Income level is transformed into bins of size 40 for classification.
 5. Each image is further split into 9 parts and mapped with corresponding income bin.

# Modeling
We use a VGG-16 model with weights pre-trained on ImageNet, but we drop the last two dense and dropout layers. We then generate useful image features from the truncated VGG-16 Model. In the end, we classify the images by income level.


