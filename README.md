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


## Context

Breast cancer is the most common cancer diagnosed in women, accounting for more than 1 in 10 new cancer diagnoses each year. It is the second most common cause of death from cancer among women in the world (M. Alkabban, 2022). In 2022, the government of Canada estimated that 28,600 Canadian women will be diagnosed with breast cancer and 5,500 will die of it. To help radiologists improve the predictive accuracy of screening mammography, computer-assisted detection and diagnosis (CAD) software have been developed and in clinical use since the 1990s. Unfortunately, data suggested that early commercial CAD systems had not led to significant improvement in performance (Fenton, J. J. et al., 2007). The average sensitivity of digital screening mammography in the U.S. is 86.9% and the average specificity is 88.9% (Lehman, C. D. et al., 2016). Detection of subclinical breast cancer on screening mammography is challenging as an image classification task because the tumors themselves occupy only a small portion of the image of the entire breast.

## Project Overview

Deep learning analysis of radiological images has the potential to improve diagnostic accuracy of breast cancer, ultimately leading to better patient outcomes. The objective of this project is to develop a deep learning algorithm that can accurately detect breast cancer on screening mammograms with only the cancer status (label) of image. We intent to surpass a 89% accuraccy with our model, making it a feaseble option for real life applications. 

## Data Source

The dataset used in this project was obtained from [CBIS-DDSM: Breast Cancer Image Dataset](https://www.kaggle.com/datasets/awsaf49/cbis-ddsm-breast-cancer-image-dataset/data) on Kaggle. (Rebecca Sawyer Lee, Francisco Gimenez, Assaf Hoogi , Daniel Rubin  (2016))


## Methodology

SOMETHING HERE

### Exploratory Data Analysis

SOMETHING HERE

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
