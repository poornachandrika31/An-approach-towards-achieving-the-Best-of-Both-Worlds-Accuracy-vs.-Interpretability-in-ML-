# Achieving-the-Best-of-Both-Worlds-Accuracy-vs.-Interpretability-in-ML-
Project Overview
This project explores machine learning-based classification for two datasets:

 Wine Quality Prediction: Predicts wine quality based on physicochemical properties.

Adult Income Prediction: Predicts whether an individual earns more than $50K per year based on demographic and work-related attributes.

A key focus of this project is to balance accuracy and interpretability to identify the best trade-off model using Pareto-optimal analysis. The interpretability of models is analyzed using SHAP (SHapley Additive exPlanations).

Datasets used:
Wine Quality Dataset

     https://archive.ics.uci.edu/ml/datasets/Wine+Quality
Description: This dataset contains physicochemical properties of red and white wine samples and their corresponding quality ratings.

Target Variable: quality (integer scale 3-9)

Features:

Numerical: fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol

Preprocessing Steps:

The target variable is converted into a binary classification problem:

Good quality (1): Quality >= 7

Bad quality (0): Quality < 7

Features are standardized for better model performance.

💰 Adult Income Dataset

    https://archive.ics.uci.edu/ml/datasets/adult
 Description: This dataset contains demographic and work-related attributes used to predict whether an individual's income exceeds $50K per year.

  Target Variable: salary (<=50K or >50K)

   Features:

   Categorical: workclass, education, marital-status, occupation, relationship, race, sex, native-country

   Numerical: age, fnlwgt, education-num, capital-gain, capital-loss, hours-per-week

 🚀 Project Workflow

I. Data Preprocessing Steps:

   1. Missing values handled by removing rows with missing entries.
   2. Label Encoding applied to categorical features.
   3. Feature scaling applied to numerical variables.
      
II.  Model Training and Evaluation:

We implement multiple machine learning models for both datasets:

| **Model**                  | **Type**                 | **Interpretability** |
|----------------------------|-------------------------|----------------------|
| Logistic Regression        | Linear Model           | High                |
| K-Nearest Neighbors (KNN)  | Instance-based Learning | Low                 |
| Support Vector Classifier (SVC) | Kernel-based Model    | Low                 |
| Decision Tree             | Tree-based Model        | High                |
| Random Forest             | Ensemble Learning       | Medium              |
| XGBoost                   | Boosted Trees          | Low                 |
| Gaussian Naïve Bayes       | Probabilistic Model    | High                |

Performance Metrics:
1. Classification Accuracy
2. Precision, Recall, F1-score
3. Confusion Matrix for error analysis.

III. Pareto-Optimal Tradeoff Analysis
Goal: Identify models that optimize both accuracy and interpretability.

Interpretability Scoring:

   1. Complexity Score: Based on the number of decision rules or model parameters.
   2. Feature Usage Score: Fraction of features contributing significantly to predictions.
   3. Explainability Score: How easily a model’s decisions can be explained.

Pareto Front Computation:
A Pareto-optimal frontier is plotted to show models that are non-dominated in accuracy vs. interpretability space. The best trade-off model is chosen from the Pareto front.

IV. SHAP (SHapley Additive Explanations) Analysis
SHAP reasons, or Shapely Additive reasons, is a powerful method that enhances machine learning models' explainability by providing both local and global explanations of predictions. It simplifies complex models such as Random Forest and XGBoost by making them easier to understand and interpret by showing each feature's contribution to the predictions of the model.  Both in Adult Income Prediction and Wine Quality Prediction, SHAP can be utilized to explain how each feature affects the model's output.

V. Confusion Matrix Analysis
A confusion matrix is plotted for the best trade-off model to evaluate misclassifications.It Helps in understanding false positives (FP) and false negatives (FN).

VI. Results & Insights 

| Dataset       | Best Trade-Off Model  | Accuracy | Interpretability Score |
|--------------|----------------------|----------|------------------------|
| Wine Quality | Logistic Regression  | 0.87     | 3.5                    |
| Adult Income | XGBoost              | 0.86     | 3.5                    |

Wine Quality: Decision Trees perform well in terms of both accuracy and interpretability.

Adult Income: Logistic Regression provides the best trade-off.

SHAP Analysis:
1. Wine Quality: alcohol, volatile acidity, and sulphates are key predictors.
2. Adult Income: education, capital-gain, and occupation are the most important features.
