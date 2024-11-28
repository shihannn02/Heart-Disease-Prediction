## Heart Disease Prediction

### Dataset Introduction

This is a heart disease prediction dataset that encompasses 14 predictor variables and 1 target variable. There are totally 6 numerical features and 7 categorical features, excluding the target variable. While bearing similarities to the widely-used heart disease dataset on [Kaggle](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset), this dataset  presents distinct characteristics, particularly in its missing data distribution. Notably, several features exhibit substantial missing values: **ca** at 65.7%, **thal** at 52.3%, **slope** at 31.1%, and **fbs** at 11.0%, while other features show a slight missing data. This distinguishes it from conventional heart disease datasets, introducing additional complexity to the modeling process and requiring careful consideration in the data preprocessing phase.

### Model Introduction

To address the missing value, multiple approaches were evaluated, including `drop features(or instance)`, `K-Nearest Neighbors (KNN) imputation`, `mode imputation`, and `Random Forest imputation`. Comparative analysis of these methods revealed that Random Forest imputation demonstrated superior performance in maintaining data integrity and predictive accuracy. Based on these empirical results, Random Forest imputation was selected as the optimal method for handling missing values in our subsequent analysis pipeline.

I implemented and evaluated three machine learning algorithms: `Logistic Regression` with hyperparameter optimization through grid search, `Random Forest` with Asynchronous Successive Halving Algorithm (ASHA) tuning, and `XGBoost` incorporating grid search and cross-validation. Among these models, XGBoost demonstrated superior predictive performance, achieving an accuracy of 56.3%. To further enhance model performance, I also addressed the inherent class imbalance in the dataset. While both upsampling and downsampling techniques are common approaches for handling class imbalance, considering the relatively small sample size of the dataset, I chose downsampling as it could lead to information loss. Therefore, we employed the `Synthetic Minority Over-sampling Technique (SMOTE)` to augment the minority classes. This approach proved effective, resulting in a substantial improvement in model performance, with accuracy increasing to 62.1%. 

For further analysis, I also printed out the evaluation metrics of Accuracy, Precision, Recall and F1-score for model with best performance and feature importance.
