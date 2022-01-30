# CityHack22 Project Submission
## Project: < Time Series Foracasting Application >
<img src="https://github.com/Maxproto/CityHack2022/blob/main/TimeSeries.png" width="200" alt="project_logo"/>

## Team: < Best >
## Members
- < Team Member 1 > (Leader) WANG Xueyao
- < Team Member 2 > NI Keyang
- < Team Member 3 > WU Yutong
- < Team Member 4 > LAN Haoheng

## Description of the Project
This is a time series forecasting project using modeling to make predictions and inform strategic decision-making in multiple areas. 

### Problem Formulation:
In the light of the given data info, our group reformulates the problem in the following way. The input data consists of 4 features, which could be viewed as common multivariable input in business or industrial analysis. The final output Y could be regarded as different values we would like to predict such as stock price, voltage, income, etc.

#### Data Understanding:
The original training dataset contains 41932 rows with each row representing a single record with 4 attributes and its corresponding time and Y value. The time is ranging from 00:00 01/01/2022 to 04:30 19/10/2022.

The following is a fragment of the original training data:
|       DateTime      |    X1    |   X2  |   X3   |   X4   |       Y      |
|:-------------------:|:--------:|:-----:|:------:|:------:|:------------:|
| 2022-01-01 00:00:00 | 2.186333 | 13.76 | 0.0663 | 0.1547 | 521163.83540 |
| 2022-01-01 00:10:00 | 2.138000 | 13.90 | 0.0910 | 0.1105 | 449066.62018 |
| 2022-01-01 00:20:00 | 2.104333 | 13.90 | 0.0806 | 0.1300 | 437394.72159 |
| 2022-01-01 00:30:00 | 2.040333 | 14.00 | 0.1183 | 0.1248 | 422107.63292 |
| 2022-01-01 00:40:00 | 1.973667 | 14.14 | 0.0624 | 0.1105 | 406923.83540 |

The following is the basic statistic summary of the original training data:
|       |      X1      |      X2      |      X3      |      X4      |       Y       |
|:-----:|:------------:|:------------:|:------------:|:------------:|:-------------:|
| count | 41932.000000 | 41932.000000 | 41932.000000 | 41932.000000 |  41932.000000 |
|  mean |   6.520033   |   12.528736  |  261.430021  |  106.260820  | 504322.861242 |
|  std  |   1.982503   |   3.212579   |  363.704356  |  169.071949  | 121948.222159 |
|  min  |   1.082333   |   1.268000   |   0.005200   |   0.024700   | 178443.835400 |
|  25%  |   4.960000   |   10.464000  |   0.085800   |   0.163800   | 401060.773570 |
|  50%  |   6.640000   |   12.870000  |   18.219500  |   15.860000  | 506391.834490 |
|  75%  |   7.983333   |   15.260000  |  473.590000  |  146.250000  | 588871.076658 |
|  max  |   13.336667  |   17.760000  |  1511.900000 |  1216.800000 | 829691.717040 |

The original testing data set consists of 10484 data without Y values and the time is ranging from 04:40 19/10/2022 to 23:50 30/12/2022. Both original training and testing data are continuous with an interval of 10 minutes.

### Data Preprocessing:
1.	90% of the data is used as the training set and 10% of the data is treated as the validation set.
2.	In order to speed up learning and make the model converge faster, we used a standard scaler to resize the distribution of the values of both the training data and test data. The value of the 4 features and Y have a mean of 0 and a standard deviation of 1 after normalization.
3.	In this project, we would like to apply an artificial recurrent neural network (RNN) architecture named Long short-term memory(LSTM) to analyze the time-series data. And we would like to consider the consistent impact of the 4 features and Y value from the past 48 hours, which is represented as 288 data. We reconstructed the training data into a training set with 41644 inputs, and each input is a 2 by 2 matrix with 288 rows and 5 columns.

### Modeling:
The structure of the LSTM model in this project is shown as below:
|    Layer (type)   |   Output Shape  | Param # |
|:-----------------:|:---------------:|:-------:|
|    lstm (LSTM)    | (None, 288, 64) |  17920  |
|   lstm_1 (LSTM)   |    (None, 32)   |  12416  |
| dropout (Dropout) |    (None, 32)   |    0    |
|   dense (Dense)   |    (None, 1)    |    33   |

## 3 Most Impactful Features of the Project (with Screenshot and Short Description (150 words))
1. < First Feature > LSTM Model
3. < Second Feature > Data Reconstruction
4. < Third Feature >  Prediction based on previous output of the model  

## Tech used (as many as required)
1. < Tech > Python API: Keras
2. < Tech > Data Visualization in Python
