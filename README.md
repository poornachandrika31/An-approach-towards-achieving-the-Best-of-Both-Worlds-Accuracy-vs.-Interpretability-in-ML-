# Achieving-the-Best-of-Both-Worlds-Accuracy-vs.-Interpretability-in-ML-
Project Overview
This project explores machine learning-based classification for two datasets:

    Wine Quality Prediction: Predicts wine quality based on physicochemical properties.

    Adult Income Prediction: Predicts whether an individual earns more than $50K per year based on demographic and work-related attributes.

A key focus of this project is to balance accuracy and interpretability to identify the best trade-off model using Pareto-optimal analysis. The interpretability of models is analyzed using SHAP (SHapley Additive exPlanations).

Datasets used:
Wine Quality Dataset

    Source: UCI Machine Learning Repository

    Target Variable: quality (integer scale 3-9)

    Features:

        Numerical: fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol

    Preprocessing Steps:

        The target variable is converted into a binary classification problem:

            Good quality (1): Quality >= 7

            Bad quality (0): Quality < 7

        Features are standardized for better model performance.

💰 Adult Income Dataset

    Source: UCI Machine Learning Repository

    Target Variable: salary (<=50K or >50K)

    Features:

        Categorical: workclass, education, marital-status, occupation, relationship, race, sex, native-country

        Numerical: age, fnlwgt, education-num, capital-gain, capital-loss, hours-per-week

    Preprocessing Steps:

        Missing values handled by removing rows with missing entries.

        Label Encoding applied to categorical features.

        Feature scaling applied to numerical variables.
