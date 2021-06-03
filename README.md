# Customer churn prediction and survival analysis in telecom, using machine learning

## Table of content
 
 - #### Introduction
 - #### Requirements
 - #### Data source
 - #### Preprocessing and descriptive data analysis
 - #### Machine learning for churn prediction
 - #### Survival analysis
 - #### Dashboard and webapp
 
 
 ## Introduction

&nbsp;&nbsp;&nbsp; The main goal of this project is to use machine learning methods for churn prediction and survival analysis with application in the telecom. By definition, customer churn is the loss of customers that are using a company's seervice after a certain time. It is an important issue especialy for businesses that provide subscription based services such as telecom companies. In fact it is known that acquiring new customers is more expensive than keeping the existing ones. Therefor it is important for companies to properly predict and develop strategies to reduce their churn rate. 


## Requierments

&nbsp;&nbsp;&nbsp; Please refer to the **requirements.txt** for a list of python packages that are required for this project. Note that sklearn is used for machine learning and lifelines is used for survival analysis.


## Data source (IBM):

&nbsp;&nbsp;&nbsp; https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv


## Preprocessing and descriptive data analysis:

&nbsp;&nbsp;&nbsp; Please refer to 'Preprocessing.ipynb' notebook for preprocessing and descriptive data analysis. In this notebook effect of different variables on the churn is visualized and investigated. Also the dataset is prepared for machine learning and survival analysis.


## Machine learning for churn prediction:

&nbsp;&nbsp;&nbsp; Please refer to 'ML_classification.ipynb' for machine learning models for churn prediction. In this notebook the following classification algorithms are used for churn prediction:

 1. Logistic regression
 2. Decision tree
 3. Random forest
 4. Ridge classifier cv
 5. XGBoost classifier
 
&nbsp;&nbsp;&nbsp; To improve the accuracy of these algorithms the hyper parameters of each algorithm is tuned through gridsearch cross validation. To compare the performance of these algorithms the accuracy metrics are evaluated on the test set. In addition, importance of diffent features of the model is evaluated in the feature importance section. In the end the models are used to predict churn base on a customers' features.

## Survival analysis:

&nbsp;&nbsp;&nbsp; Please refer to 'survival.ipynb' for survival analysis. In the case of this telecom problem the goal of survival analysis is to find the expected probability of survival (not churning) for customers during their subscription. Also to find the effect of different variables (also called covariates) on the survival probability. The following survival analysis methods are applied here:

 1. Kaplan-meyer survival curves
 2. Cox-proportional hazard model
 
&nbsp;&nbsp;&nbsp;In the Kaplan-meyer survival analysis, first the survival curve is developed for the dataset. This curve could be interpreted as the survival curve for an average customer. To better understand the effect of categoriacal variable on the survival probability of customers, the customers are stratified for each variable and survival curves are developed for each group. This will allow to better analyze the effect of each category and make more informed decision on how to mange churn. 
&nbsp;&nbsp;&nbsp;In the next part of this notebook, the Cox-proportional hazard model is applied. The Cox-proportional hazard model is a regression model which allows to develop survival curves for each individual customer. An example of predicting survival curve for a customer is shown at the end of this notebook. 