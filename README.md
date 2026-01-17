# Customer Revenue Propensity Modeling - Python Pipeline

##  Problem Statement
Targeted marketing and resource allocation are critical for maximizing customer lifetime value. This project addresses the challenge of identifying high-propensity customers within a **"Revenue Grid."** By building an automated machine learning pipeline to handle messy categorical data and missing values, the model accurately predicts a customer's revenue potential, allowing businesses to optimize their sales strategies and focus on the most profitable segments.


## Executive Summary & Key Insights
* **Model Champion:** The **XGBoost Classifier** was the top performer, achieving a near-perfect **ROC-AUC of 0.9916** on the test set.
* **Feature Importance:** Key drivers of customer revenue included variables like **Online Purchase Amount** and **Investment levels**. The model successfully captured non-linear relationships that traditional regression models missed.
* **Predictive Power:** The model demonstrates extremely high precision in identifying "Revenue Grid 1" (high-value) customers, which is critical for reducing "false positives" in marketing spend.
* **Pipeline Automation:** Developed a robust end-to-end pipeline that automates data cleaning, missing value imputation, and feature selection, significantly reducing manual preprocessing time.

## Technical Python Highlights
This project demonstrates advanced software engineering and data science practices:

* **Custom Scikit-Learn Transformers:** Created modular classes such as `VarSelector`, `string_clean`, and `DataFrameImputer` among others to integrate custom logic directly into the Scikit-Learn **Pipeline** framework.
* **Data Staging:** Implemented automated handling of categorical data using **One-Hot Encoding** while managing mixed-type missing values.
* **Hyperparameter Tuning:** Optimized model performance using **RandomizedSearchCV**, tuning parameters such as `n_estimators`, `max_depth`, and `learning_rate` specifically for the XGBoost algorithm.
* **Evaluation Metrics:** Utilized **ROC-AUC Curves**, **F1 score**, and **Confusion Matrices** to validate model performance across imbalanced classes.
* **Cross-Validation:** Employed **K-Fold cross-validation** to ensure model stability and prevent overfitting.


## Machine Learning Workflow
1. **EDA & Cleaning:** Analyzed the distribution of revenue classes and standardized inconsistent string labels using custom cleaning functions.
2. **Feature Engineering:** Automated feature selection to retain only high-variance predictors and handled missing data through custom imputation logic.
3. **Pipeline Construction:** Chained preprocessing steps using `FeatureUnion` and `Pipeline` for a streamlined, deployment-ready object.
4. **Model Comparison:** Evaluated **Logistic Regression**, **Random Forest**, and **XGBoost** to find the optimal balance of speed and accuracy.
5. **Optimization:** Fine-tuned the final XGBoost model to minimize Log-Loss and maximize classification accuracy.
