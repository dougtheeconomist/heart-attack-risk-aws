# heart-attack-risk-aws
Full lifecycle modeling of heart attack risk using AWS services

## Introduction

The purpose of this study is to create and deploy a machine learning model to predict the risk of heart failure based on an array of health measures in a full stack AWS cloud environment. This means specifying and training a model in SageMaker using data stored in S3, setting up an endpoint to access this model using Lambda, and finally utilizing API Gateway to allow a user to access the model from the web in order to get a prediction based on input data. 

## The Data

In order to train my model I used a dataset found on Kaggle, specifically [this dataset](https://www.kaggle.com/rashikrahmanpritom/heart-attack-analysis-prediction-dataset), which contains several hundred observations. Each observation includes data recorded from a single individual on 14, including the target factor for our prediction, which is the diagnosis of heart disease, a brief description of these variables have been included in the following table.

|Observed Variables                                   | Variable Type|
|-----------------------------------------------------|:-------------------|
| Age                                                 | Integer            |
| Sex                                                 | Boolean            |
| Chest pain type(if present)                         | Categorical        |
| Resting blood pressure                              | Integer            |
| Serum cholestoral in mg/d1                          | Integer            |
| Fasting blood sugar > 120 mg/dl                     | Boolean            |
| Resting electrocardiographic results                | Categorical        |
| Maximum heart rate achieved                         | Integer            |
| Exercise induced angina                             | Boolean            |
| ST depression induced by exercise relative to rest  | Float              |
| Slope of the peak exercise ST segment               | Categorical        |
| Number of major vessels (0-3) colored by flourosopy | Integer            |
| Thal rate                                           | Categorical        |
| Diagnosis of heart disease                          | Boolean            |

This data is relatively clean and contains no missing values. The only real cleaning required was to format the data to be compatible with the way that Sagemaker is set up to read the data by default. 