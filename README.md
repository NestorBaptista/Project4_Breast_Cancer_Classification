# Project4_Breast_Cancer_EDA

## Table of content

- [Context](#context)
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Methodology](#methodology)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Model Architecture](#model-architecture)
    - [Initial Model](#initial-model)
    - [Optimized Model](#optimized-model)
- [Summary](#summary)
- [References](#References)


## Context

Breast cancer is the most common cancer diagnosed in women, accounting for more than 1 in 10 new cancer diagnoses each year. It is the second most common cause of death from cancer among women in the world (M. Alkabban, 2022). In 2022, the government of Canada estimated that 28,600 Canadian women will be diagnosed with breast cancer and 5,500 will die of it. To help radiologists improve the predictive accuracy of screening mammography, computer-assisted detection and diagnosis (CAD) software have been developed and in clinical use since the 1990s. Unfortunately, data suggested that early commercial CAD systems had not led to significant improvement in performance (Fenton, J. J. et al., 2007). The average sensitivity of digital screening mammography in the U.S. is 86.9% and the average specificity is 88.9% (Lehman, C. D. et al., 2016). Detection of subclinical breast cancer on screening mammography is challenging as an image classification task because the tumors themselves occupy only a small portion of the image of the entire breast.

## Project Overview

Deep learning analysis of radiological images has the potential to improve diagnostic accuracy of breast cancer, ultimately leading to better patient outcomes. The objective of this project is to develop a deep learning algorithm that can accurately detect breast cancer on screening mammograms with only the cancer status (label) of image. We intent to surpass a 89% accuraccy with our model, making it a feaseble option for real life applications. 

## Data Source

The dataset used in this project was obtained from [CBIS-DDSM: Breast Cancer Image Dataset](https://www.kaggle.com/datasets/awsaf49/cbis-ddsm-breast-cancer-image-dataset/data) on Kaggle. (Rebecca Sawyer Lee, Francisco Gimenez, Assaf Hoogi , Daniel Rubin  (2016))


## Methodology

Started with deciding exactly what kind of data we wanted to work with. Healthcare was decided. Looked into different topics and decided on breast cancer. For the machine learning component, we decided it might be interesting to work with images based on the powerful models that could be created to predict images. Overall intrigued with how models would progress and if any features would prove to explain the reason behind the models and if there were any potential outliers. Through data exploration we were able to look closer at what elements would be required to complete our objectives. We initally worked with our datasets and the images through google colab. As there was nearly 5 GB worth of image data, we thought it would be beneficial to see if there were alternative routes to hosting the data. The data was later moved to AWS. The data, images, and models were all compatible. Images were held in buckets and model pulled image data from buckets successfully and executed the code. Through deep learning models we were able to classify the classifications of these breast cancer images benign, benign without callback, and malignant to about 86% accurracy. Through exploratory data analysis we were able to look at individual features more closely to see their impact on the model and breast cancer as a whole. Made some conclusion statements from all our findings.

### Exploratory Data Analysis

Started by isolating the breast cancer classifications (benign, benign without callback, and malignant) into respective DataFrames for both the mass and calcification data. Took a deeper look at mass shape, calcification distribution, and subtlety levels for both mass and calcification data. Using value_counts able to determine which characteristics and subtlety levels seemed to appear the most across the data. Plotted this information into bar and pie charts using matplotlib. Through the visualizations a few conclusions can be drawn that may have influenced the models performance and classifying classification of breast cancer through images. From analyzing the mass shape data, we were able to determine that the most reported shape was different between all of the classifications. From the model perspective this would be beneficial because it is easier to classify between benign, benign without call back and malignant. It is good for physicians and radiologists reviewing the images because it will help with correctly diagnosing and treatment plans. From analyzing the subtlety levels of the mass shapes we were able to determine that most frequest level was 5. Meaning that the shapes in these images were very visible and easily distguishable. Futher supporting both the models performance and abiility to classify the classifications correctly. From analyzing the calcification description data, we were able to determine that benign and malignant share the same most seen description, clustered. This can lead to the model performance being effected due the fact the anatomy of the calcification in the images is so similar. Also proves problematic for healthcare professionals to consistently correctly diagnose from the image alone. That is why it is crucial for healthcare professionals to continue usings other methods to correctly determine the correct calcification classification for these images and future images. Methods such as blood work and other types of medical imaging. At least when it comes to the benign without callback, it has a clear distinction from the others and supports the "without callback" meaning a physician has marked down this calcification as being note worthy, but the patient isn't currently at risk of breast cancer and no follow up is needed at this time. From analyzing the subtlety levels of the calcification data, we were able to determine that both benign and malignant share the same level of three further supporting that the images could be misinterpreted by both the model and healthcare professionals. The subtlety levels do seem fairly well distributed for all the classifications in comparison to the mass subtlety levels. Across both the mass and calcification subtlety levels, we are able to see that it is very small number of the images that actually have subtlety level of 1. That means overall it's a great feature for distinguishing classifications due to the fact it is easier to recognize both masses and calcifications on the images helping model performance and healthcare professionals. 

To get the statistical information and map visuals, the data was taken from https://gis.cdc.gov/Cancer/USCS/#/AtAGlance/ giving us information on the new cases of breast cancer and reported deaths of breast cancer in each state of the United States in 2020. We read the csv and created a DataFrame for the new cases. We cleaned the dataframe dropping any unecessary columns. Assigned the two letter 'ISO' code to the corresponding state to successfully plot a map of each state on a color scale for the amount of new cases using plotly choropleth. Then got the average number, the total number, and the states with the highest and lowest new cases. The same methodology was used for the choropleth map visual and basic statistical analysis of the recorded deaths data. 

### Model Architecture

Our initial model architecture was designed as follows:

*AREFIN EXPLAIN HERE*

#### Initial Model

- **First Hidden Layer:** 50 neurons, relu activation
- **Second Hidden Layer:** 20 neurons, relu activation
- **Output Layer:** 1 neuron, sigmoid activation
- **Training Epochs:** 100

#### Optimized Model

- **First Hidden Layer:** 100 neurons, relu activation
- **Second Hidden Layer:** 50 neurons, relu activation
- **Third Hidden Layer:** 20 neurons, sigmoid activation
- **Fourth Hidden Layer:** 10 neurons, sigmoid activation
- **Output Layer:** 1 neuron, sigmoid activation
- **Training Epochs:** 100

## Summary

*CONCLUSION OF MODEL PERFORMANCE*

## References

References for creating choropleth map visual

https://plotly.com/python/choropleth-maps/

https://towardsdatascience.com/simplest-way-of-creating-a-choropleth-map-by-u-s-states-in-python-f359ada7735e

Reference for assigning ISO code to a dataframe with the state in a column already exisiting

https://stackoverflow.com/questions/66572349/python-sub-state-names-for-abbrev-via-python-dict-with-re-sub
