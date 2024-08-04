# Lag-Llama: Towards Foundation Models for
Probabilistic Time Series Forecasting


## Project Report

### Contents

1. [Motivation](#motivation)
2. [Introduction](#introduction)
3. [Dataset](#dataset)
4. [Steps & Methodology](#steps--methodology)
5. [Results](#results)
6. [Additional Information](#additional-information)
7. [Key Findings](#key-findings)
8. [Future Work](#future-work)
9. [Conclusion](#conclusion)
10. [References](#references)

---

### Motivation

The detection of anomalies in time series data is critical for identifying faults, unusual events, or significant deviations in various applications, including manufacturing, finance, and healthcare. The primary motivation behind this project is to leverage the Lag-Llama model to accurately identify anomalies in a given dataset, thereby providing a robust tool for monitoring and maintaining system integrity.

### Introduction

Anomalies represent significant deviations from expected behavior in datasets and can indicate critical issues needing attention. This project employs the Lag-Llama model, a deep learning-based approach, to predict and detect anomalies in time series data. The report outlines the data preprocessing, model training, evaluation, and anomaly detection methodologies, along with the results obtained.

### Dataset

The dataset comprises multiple files containing time series data for different bearings (Bearings 1 to 4). The data was loaded in chunks due to its large size and merged into a single DataFrame for processing. The index was set to a date range starting from '2000-01-01', and the mean of the absolute values was calculated for each chunk.

#### Example of Merged Data:
```plaintext
            Bearing 1  Bearing 2  Bearing 3  Bearing 4
2000-01-01   0.061636   0.074461   0.079850   0.043428
2000-01-02   0.060954   0.074154   0.077601   0.043864
2000-01-03   0.054737   0.071524   0.071931   0.040119
2000-01-04   0.118732   0.076435   0.078924   0.051461
2000-01-05   0.118869   0.079039   0.079826   0.050557
Steps & Methodology
Data Preprocessing:

Loaded data in chunks.
Calculated mean of absolute values for each chunk.
Merged chunks into a single DataFrame.
Set date range as the index.
Dataset Preparation:

Split data into training and testing datasets.
Training range: '2004-02-12 11:02:39' to '2004-02-13 23:52:39'.
Testing range: from '2004-02-13 23:52:39' onwards.
Model Configuration:

Prediction Length: 48
Context Length: 32
Other parameters as per the pretrained model's checkpoint.
Model Training & Prediction:

Loaded pretrained model checkpoint.
Created Lag-Llama model with appropriate parameters.
Transformed training data for the model.
Generated predictions on the test dataset.
Evaluation:

Used several metrics: MSE, Absolute Error, MAPE, sMAPE, and Coverage at different quantiles.
Anomaly Detection:

Set a threshold for anomaly detection.
Flagged anomalies where the absolute difference between actual and predicted values exceeded the threshold.
Results
The evaluation metrics indicated the following:

MSE: 0.005657
Absolute Error: 1.508
MAPE: 0.198
sMAPE: 0.255
Coverage[0.5]: 0.458
RMSE: 0.075
Additional Information
The attached image (image.png) contains a plot showing the detected anomalies, with the significant deviations between actual and predicted values highlighted.

Example Anomaly Detection Plot:

Key Findings
The Lag-Llama model effectively predicted the time series data and detected anomalies.
Evaluation metrics such as MSE, MAPE, and sMAPE provided insight into the model's accuracy and performance.
Setting an appropriate threshold is crucial for accurate anomaly detection.
Future Work
Experiment with different prediction and context lengths.
Fine-tune the model's hyperparameters for better performance.
Implement additional preprocessing steps to handle data irregularities.
Explore other anomaly detection techniques for comparative analysis.
Conclusion
The Lag-Llama model demonstrated its capability in predicting time series data and detecting anomalies effectively. While the initial results are promising, further improvements and fine-tuning can enhance the model's accuracy. This project lays the groundwork for robust anomaly detection systems in various applications.
