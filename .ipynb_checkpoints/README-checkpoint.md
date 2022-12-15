EPFL Machine Learning Course CS-433  

Team:
- Andres Odile
- Giraud-Sauveur Félicie
- Miesen Sander

# Project 2: Covid-19

The objective of this project is to build a maching learning model to predict whether a patient infected with Covid-19 will die or not.

## 1. Data and set up

### 1.1. Origin of the data

The studied dataset stems from the Infectious Diseases Data Observatory (IDDO) Data Repository of COVID-19 data.
The IDDO aims to assemble clinical, laboratory and epidemiological data on a collaborative platform to be shared with the research and humanitarian communities. The repository contains individual patient data on poverty-related diseases and emerging infections, such as SARS-CoV2 (causing COVID-19), Ebola virus disease or malaria. To ease the analysis of the data, the repository is harmonised with the CDISC SDTM data standard.

The data was pulled from the underlying data collection projects on 2022-09-01. The data comes from 1,200 institutions from over 45 countries and gathers various information from 700,000 hospitalised individuals. The non-exhaustive list of features contains information such as sex, country of origin, blood levels of various hormones, or if the patient has been vaccinated…

### 1.2. Data importation

First, all of the data has to be downloaded from the link. This includes both the data dictionary file and all of the studies’ data contained in the DATA_2022-09-01 folder. 

There are a few things to do to set up the data correctly. Two files have to be unzipped and put into the DATA_2022-09-01 folder with the others. 
The data dictionary file is given in the .xlsx, or Excel worksheet format. This file format has to be changed to the .csv or Excel comma-separated-vector one (can be done by opening it in Excel and downloading in the wanted format). The file also has to be renamed by replacing blank spaces by underscores, giving IDDO_SDTM_Data-Dictionary_v3.0_2022-10-06.csv as the final file name. 

### 1.3. Repository structure 

For our project files to run smoothly, the repository needs to have a particular architecture to avoid the need to change all of the file paths. It can easily be achieved through the following guidelines :
If not done already, clone the project repository locally
In the project’s main directory, create a subdirectory called data and put the data dictionary file and the DATA_2022-09-01 folder in it (do not put the data dictionary file in the DATA_2022-09-01 folder!)
Within the data subdirectory, create another subdirectory called results. This will be used to store the notebook output results. 

## 2. Structure of the project

There are three files that must be run in the right order:

- I_data-selection:

Selects the columns of interest in each data file (original data) +  Makes the necessary transformations (e.g. transform 'unknown' into NA, homogenise the units, etc.) + Finally creates the final data matrix.

- II_feature-selection:

Stratifies per continent + Pre-process the data (NA, standardization, etc...) + Chooses which features to keep from the matrix extracted from the "I_data-selection" file.

- III_models-and-predictions:

Tests and compares several models (Logistic regression, K-Nearest Neighbour Classifier, Support Vector Machines, Multi-layer perceptrons, Quadratic discriminant analysis and XGBoost) on the matrix extracted from the "II_features-selection" file (training with data from Europe only) + Improves the best models and analyses it + Applies the model to other continents.


