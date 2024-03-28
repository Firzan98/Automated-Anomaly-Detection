# Automated-Anomaly-Detection

Problem Statement:
Many different industries need predictive maintenance solutions to reduce risks and gain actionable insights through processing data from their equipment.
Although system failure is a very general issue that can occur in any machine, predicting the failure and taking steps to prevent such failure is most important for any machine or software application.
Predictive maintenance evaluates the condition of equipment by performing online monitoring. The goal is to perform maintenance before the equipment degrades or breaks down.
This project is aimed at predicting the machine breakdown by identifying the anomalies in the data.
The data we have contains about 18000+ rows collected over few days. The column ‘y’ contains the binary labels, with 1 denoting there is an anomaly. 
The rest of the columns are predictors.  

# Data Description:
1. Time : This column marks the timestamp as to when , data for that row was recorded. In this dataset the period between each observation is 2 seconds.
2. Columns x1 to x60 : All of these columns are predictors determining the presense of anomalies. We unfortunately do not have access to the information about the nature of each independant column. These columns are numeric in nature.
3. Column y.1 : This column is also a predictor. Once again we unfortunately do not have access to the information about the nature of this column. This column is binary in nature.
4. Column y : Represents our output variable which we aim to accurately predict. It represents the presence of anomalies at that point in time.


## A. Model Building
Our project was built with the aim of builing a model capable of predicting the existance of an anomaly.
I have first checked the data and found no correlation between the time variable and our output variable, hence i dropped the time column and converted the dataset into a crosssectional dataset.
Exploratory Data Analysis was performed which revealed the high degree of class imbalance and skewness of features.
Next we moved onto Data Pre Processing which involved application of power transforms to rectify skewness.
We applied Standardization on our dataset to bring all our numeric features to one scale.
Next we created our Feature Matrix X and dependant variable y and split the data into training and testing parts.
At this point we dealt with class imbalance by oversampling the minority class.
Finally We built and trained 3 Models - Decision Tree , Random Forest and Net-Elastic Logistic Regression for our dataset
We fine tuned the hyperparameters for each model by running multiple CrossValidations (GridSearchCV) , this resulted in the best versions of each Model.
We calculated the performance metrics for each model and compared them to find the best model among the 3.
This led us to pick the Random Forest as our Model for this Classification Problem

## B. Model Deployment
We picked the real time inference method for deploying our model.
In our deployed model we created pipelines to combine feature engineering and implementation of the model.
We also created a pipeline for hyperparameter tuning.
We constructed all the nessessary architectures involved to deploying the model.

## C. Links 
1. The Endpoint the model is saved in is:

anomanly-rfc-pipeline-real-time-2024-03-28-12-05-29-794

2. Model storage location: 

s3://sagemaker-eu-north-1-730335315002/rfc-pipeline-run-2024-03-28-11-25-41-602/output/model.tar.gz

