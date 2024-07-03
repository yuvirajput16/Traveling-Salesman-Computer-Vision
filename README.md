# Traveling-Salesman-Computer-Vision
## Introduction

This repository contains code for calculating the distance travelled by Traveling Salesman using computer vision techniques. The dataset used in this project is available on Kaggle: [Traveling Salesman Computer Vision](https://www.kaggle.com/datasets/jeffheaton/traveling-salesman-computer-vision/data).


## Dataset Description

The dataset consists of three CSV files with the following columns:

- **id**: A unique identifier.
- **filename**: Name of the map's image file.
- **distance**: Total distance through the cities (label).
- **key**: Generator filename providing dimensions, city count, and distance.

## Dataset Preprocessing

The dataset preprocessing involves extracting information from the 'key' column to determine width, height, and city count. Additionally, images are resized using padding and preprocessed for model training.

## Dataset Challenges

- **Scaling Maps**: Proper scaling without losing size information.
- **Overlapping Paths**: Handling overlapping paths to avoid misleading ratios.
- **Color Brightness**: Managing brightness due to overlapping paths and cities.

## Solutions Implemented

### 1. Resize Images

Images are resized to `(1024, 1024)` using padding to retain size information. For computational efficiency, a smaller size of `(200, 200)` is used during training.

### 2. Model Architecture

A Convolutional Neural Network (CNN) followed by dense layers is used for regression. The model predicts the total path length based on the input images.

## Training and Evaluation

The model is trained using the resized images and evaluated using test data. The evaluation metric used is the R-squared (r2) score, which measures the goodness of fit of the model.

## Results

After training for 15 epochs, the model achieves an r2 score of `0.94` on test datset, indicating a good fit to the data.
