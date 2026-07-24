---
title: "Predicting Hospital Patient Readmission by Analyzing Electronic Health Record with Interpretable Machine Learning"
collection: publications
category: manuscripts
permalink: # none
excerpt: "This research employs eleven machine learning algorithms to predict patient hospital readmissions from historical data while also identifying the most influential features for that prediction."
date: 2024-10-01
venue: 'Eurasian Journal of Mathematical and Computer Applications'
paperurl: 'https://ejmca.enu.kz/assets/files/12-4-3.pdf'
citation: # none
bibtexurl: "https://hbunyamin.github.io/files/ejmca-2024-readmission.bib"
---

Hospital patient readmission is defined as a situation where a patient is treated again in a hospital after she is discharged within a specific time frame: 30 days, for example. This research aims to predict whether or not a patient will be readmitted from a hospital by applying predictive modeling which is learned from historical data. Our patient dataset is extracted from MIMIC-IV, which consists of an electronic health record dataset in Beth Israel Deaconess Medical Center (BIDMC) from year 2008 to 2019. Our experiments utilize four categories of models that are linear (logistic regression and linear discriminant analysis), non-linear (K-nearest neighbors, na¨ive Bayes, decision tree, and support vector machines), ensemble (bagging classifier, random forests, and extra trees), and boosting models (adaboost, stochastic gradient boosting). The performance evaluation of each model is using balanced accuracy because of imbalanced classes in our dataset. Additionally, each model is processed through 10-fold cross-validation and followed by a hyperparameter tuning process which eventually reports that the tree-based models, such as decision trees, extra trees, and random forests achieve the highest balanced accuracy. This study also identifies the features that significantly influenced the model’s predictions by utilizing the cumulative reduction in both the mean and standard deviation of impurity and two global model-agnostic techniques, that are permutation feature importance (PFI) and SHapley Additive exPlanations (SHAP). The results obtained from these three different approaches are consistent, highlighting that the average levels of hematocrit, sodium, and platelets in the blood, coupled with the duration between a patient’s registration and discharge from the hospital are critical features that have a substantial impact on the prediction outcomes.
