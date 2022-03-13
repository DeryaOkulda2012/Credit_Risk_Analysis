# Credit_Risk_Analysis

## Overview

Using data preparation, statistical reasoning, and machine learning we solve a real-world challenge: credit card risk.

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we’ll need to employ different techniques to train and evaluate models with unbalanced classes. We use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, we use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, we compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once done, we evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.


## Executive Summary of Results:

- All models showed greater than 0.61 recall score in predicting high risk credit applications.

- Yet, no single model gave high confidence when predicting high risk credit applications.

- Easy Ensemble AdaBoost Classifier had the highest recall with 0.91 in preedicting high risk credit applications.


## Naive Random Oversampling

Model Accuracy = 0.6366972052004142

!["images/01_NaiveRandom2.png"](images/01_NaiveRandom2.png)


## SMOTE Oversampling

Model Accuracy = 0.6302712208564487

!["images/02_SMOTE2.png"](images/02_SMOTE2.png)


## Undersampling

Model Accuracy = 0.5293318990697431

!["images/03_UnderSamp2.png"](images/03_UnderSamp2.png)


## Combination (Over and Under) Sampling

Model Accuracy = 0.6375533316412246

!["images/04_Combi2.png"](images/04_Combi2.png)


## Balanced Random Forest Classifier

Model Accuracy = 0.7877672625306695

!["images/05_RandomForest2.png"](images/05_RandomForest2.png)


## Easy Ensemble AdaBoost Classifier

Model Accuracy = 0.925427358175101

!["images/06_AdaBoost2.png"](images/06_AdaBoost2.png)


## Summary and Recommendations

With a 0.925 accuracy and 0.91 recall score, the Easy Ensemble AdaBoost Classifier produced the best results when predicting high risk credit applications.

Given the features used to classify each group of potential loans, the summary dataframes and individual model testing above show that both Easy Ensemble AdaBoost and Random Forest Classifiers outperformed the Resampling techniques in accurately predicting high-risk credit card applicants vs. ones with low-risk. In the case of screening for high-risk individuals, high sensitivty outweighs precision performance of the model--it is better to minimize false negatives and let those high-risk indivudals slip through the test undetected, in the instance of protecting the interests of the loaning companies.

Recommendation Based on Model (6) Performance However, all 6 models produced very low precision scores. In other words, at best, machine learning produced a 9% reliability that those that were identified as high-risk, were actually high risk. With a 91% chance of a False Positive result, where a low-risk applicant is lableed as high-risk, I cannot recommend any of the models tested in this project for implementation--regardless of high sensitivity, financial institutions risk losing 91% of future customers and revenues of low-risk applicants when they are rejected for a credit-card. A group of these False Positives will file a claim and resolve the declined application, but many will take their business elsewhere, unwilling to take on the headache of disputing the decision with the credit card company.


