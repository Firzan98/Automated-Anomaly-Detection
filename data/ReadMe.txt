Problem Statement:

Many different industries need predictive maintenance solutions to reduce risks and gain actionable insights through processing data from their equipment.

Although system failure is a very general issue that can occur in any machine, predicting the failure and taking steps to prevent such failure is most important for any machine or software application.

Predictive maintenance evaluates the condition of equipment by performing online monitoring. The goal is to perform maintenance before the equipment degrades or breaks down.

This project is aimed at predicting the machine breakdown by identifying the anomalies in the data.

The data we have contains about 18000+ rows collected over few days. The column ‘y’ contains the binary labels, with 1 denoting there is an anomaly. 

The rest of the columns are predictors.  



## Data Description:

1. Time : This column marks the timestamp as to when , data for that row was recorded. In this dataset the period between each observation is 2 seconds.

2. Columns x1 to x60 : All of these columns are predictors determining the presense of anomalies. We unfortunately do not have access to the information about the nature of each independant column. These columns are numeric in nature.

3. Column y.1 : This column is also a predictor. Once again we unfortunately do not have access to the information about the nature of this column. This column is binary in nature.

4. Column y : Represents our output variable which we aim to accurately predict. It represents the presence of anomalies at that point in time.