# Student-Academic-Performance-Analysis
----
## Overview 

This project implements a supervised regression modeling framework to predict `Exam_Score` using demographic, academic, and behavioral features. The objective is to evaluate the predictive structure of student performance and determine whether linear or nonlinear modeling approaches provide superior generalization performance. The analysis follows a structured machine learning workflow including preprocessing, model comparison, cross-validation, hyperparameter tuning, and holdout test evaluation.

----

## Objectives

* Predict `Exam_Score` using structured regression models
* Compare linear, regularized, and nonlinear approaches
* Evaluate model generalization using cross-validation and a holdout test set
* Identify the most stable and interpretable predictive model

------

## Methodology

### Data Splitting

The dataset is divided into:

* 70% Training Set
* 30% Holdout Test Set

All model selection and hyperparameter tuning are conducted exclusively on the training set using 10-fold cross-validation to prevent data leakage.

### Preprocessing

Preprocessing is implemented using scikit-learn pipelines to ensure consistent transformations across folds:

* Numerical Features
** Missing values imputed using mean
** Standard scaling applied for scale-sensitive models
* Categorical Features
** Missing values imputed using most frequent category
** One-hot encoding

Missing values imputed using most frequent category

* Standard preprocessing (no scaling; used for tree-based models)
* Scaled preprocessing (imputation + scaling; used for linear/SVR models)

----

### Models Evaluated

The following regression models were compared:

* Dummy Regressor 
* Linear Regression
* Ridge Regression
* Lasso Regression
* Elastic Net
* Support Vector Regression (SVR)
* Decision Tree Regressor
* Random Forest Regressor
* XGBoost Regressor

Hyperparameters tuning was performed using grid search.

### Evaluation Metrics

Model performance was assessed using:

* Root Mean Squared Error (RMSE) 
* Mean Absolute Error (MAE)
* $R^2$ (Coefficient of Determination)

RMSE was the primary metric due to it penalizing larger prediction errors more heavily.

----

## Results Summary

* Linear models performed consistently and achieved the best cross-validated performance.
* Ridge Regression achieved the lowest RMSE and was selected as the final model.
* Nonlinear tree-based and boosting methods did not outperform linear approaches.
* The final model achieved approximately 75% variance explained on the holdout test set.

----

## Conclusions

* Regularization provided slight improvements over standard linear regression.
* Model complexity did not meaningfully improve generalization performance.
* Prediction errors were small relative to the exam score scale.
* Mild underprediction was observed among high-performing students.

----

## Future Improvements

* Further feature engineering 
* Subgroup performance analysis
* Ensemble methods

----