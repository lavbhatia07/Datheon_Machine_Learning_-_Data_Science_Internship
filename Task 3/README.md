<div align="center">

# 📉 Customer Churn Prediction

### Machine Learning for Understanding and Predicting Customer Attrition

A machine learning project that identifies customers who may leave a telecom service using **Random Forest** and **XGBoost**.

<br/>

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Model-189E5B?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

</div>

---

## 📌 Overview

Customer churn occurs when a customer stops using a company's products or services. Predicting churn helps businesses identify customers who may leave and take steps to improve retention.

This project uses the **Telco Customer Churn dataset** to build and compare two supervised machine learning models:

- 🌲 **Random Forest Classifier**
- 🚀 **XGBoost Classifier**

The workflow covers data exploration, preprocessing, class-imbalance handling, model training, cross-validation, evaluation, and feature-importance analysis.

## 🎯 Project Objectives

- Explore customer demographics, subscribed services, account details, and billing information.
- Prepare numerical and categorical data for machine learning.
- Address target-class imbalance using class weighting.
- Train and compare Random Forest and XGBoost.
- Evaluate model performance using ROC-AUC and other classification metrics.
- Identify features that contribute most to model predictions.

## 📂 Dataset

The project uses the **Telco Customer Churn** dataset.

| Dataset detail | Description |
|---|---|
| Records | 7,043 customers |
| Columns | 21 |
| Prediction target | `Churn` |
| Target values | `Yes` / `No` |
| Problem type | Binary classification |

### Feature groups

| Group | Example fields |
|---|---|
| Customer details | `gender`, `SeniorCitizen`, `Partner`, `Dependents` |
| Account details | `tenure`, `Contract`, `PaperlessBilling`, `PaymentMethod` |
| Services | `InternetService`, `OnlineSecurity`, `TechSupport`, `StreamingTV` |
| Billing | `MonthlyCharges`, `TotalCharges` |
| Target | `Churn` |

> **Target encoding:** `No = 0`, `Yes = 1`. The `customerID` column is removed because it is an identifier rather than a useful customer-behaviour feature.

## ⚙️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Data manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine learning | Scikit-learn |
| Gradient boosting | XGBoost |
| Model persistence | Joblib |
| Development | Jupyter Notebook |

## 🔄 Machine Learning Workflow

```text
Telco Customer Churn Dataset
            │
            ▼
     Data Exploration
            │
            ▼
       Data Cleaning
  • Remove customerID
  • Convert TotalCharges to numeric
            │
            ▼
      Preprocessing
  • Impute missing values
  • Scale numerical features
  • One-hot encode categories
            │
            ▼
    Stratified Train/Test Split
            │
            ▼
     Class Imbalance Handling
            │
            ▼
      Model Training
       ┌────┴─────┐
       ▼          ▼
 Random Forest  XGBoost
       └────┬─────┘
            ▼
      Model Evaluation
  • Classification metrics
  • ROC-AUC and cross-validation
  • Confusion matrix and ROC curve
            │
            ▼
   Feature Importance Analysis
            │
            ▼
      Save Best Pipeline
```

## 🧠 Models Implemented

### 1. Random Forest

An ensemble learning algorithm that combines predictions from multiple decision trees. The model uses `class_weight="balanced"` to account for the imbalance between churn and non-churn customers.

### 2. XGBoost

A gradient-boosting algorithm that builds trees sequentially to improve predictive performance. The `scale_pos_weight` parameter is calculated from the training data to account for class imbalance.

## 🧹 Preprocessing

- Remove the `customerID` identifier.
- Convert `TotalCharges` to numeric; invalid or blank values become missing values.
- Impute missing numerical values using the median.
- Impute missing categorical values using the most frequent value.
- Apply `StandardScaler` to numerical features.
- Apply `OneHotEncoder(handle_unknown="ignore")` to categorical features.
- Use a stratified train-test split to preserve class proportions.

Preprocessing is performed inside Scikit-learn pipelines so transformations are fitted on training data rather than the held-out test data.

## 📊 Model Evaluation

The models are evaluated using:

| Metric | Purpose |
|---|---|
| Accuracy | Overall proportion of correct predictions |
| Precision | How many predicted churn cases are actual churn cases |
| Recall | How many actual churn cases are identified |
| F1-score | Harmonic mean of precision and recall |
| ROC-AUC | Ability to distinguish churn from non-churn customers |
| 5-fold CV ROC-AUC | Performance consistency across training folds |

### Visualizations

The notebook generates:

- **ROC curve comparison** — compares the discrimination performance of both models.
- **Confusion matrix** — shows correct and incorrect predictions for the selected model.
- **Top 10 feature importance** — highlights the features with the highest model importance.

> **Performance note:** The project target is ROC-AUC greater than **0.80**. Actual scores should be taken from the notebook output. No benchmark result is claimed here.

## 🗂️ Repository Structure

```text
customer-churn-prediction/
│
├── customer_churn.csv
├── customer_churn_prediction.ipynb
├── customer_churn_model.pkl
├── requirements.txt
└── README.md
```

`customer_churn_model.pkl` is generated when the notebook is run. The dataset and model file may be excluded from a public repository depending on dataset licensing and file-size considerations.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/lavbhatia07/Datheon_Machine_Learning_-_Data_Science_Internship.git
cd <your-repository>
```

### 2. Create a virtual environment (recommended)

**Windows**
```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS / Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add the dataset

Place `customer_churn.csv` in the project root, alongside the notebook.

### 5. Run the notebook

```bash
jupyter notebook customer_churn_prediction.ipynb
```

Run the notebook cells in order. It trains both models, evaluates them, displays visualizations, and saves the selected fitted pipeline as:

```text
customer_churn_model.pkl
```

## 💾 Load the Saved Model

After running the notebook, load the saved pipeline with Joblib:

```python
import joblib

model = joblib.load("customer_churn_model.pkl")

# Example: predict churn for a customer DataFrame
# The input must contain the same feature columns used during training.
predictions = model.predict(customer_data)
probabilities = model.predict_proba(customer_data)[:, 1]
```

The pipeline includes preprocessing, so input data should contain the original feature columns (excluding `customerID` and `Churn`).

## 🔮 Possible Future Improvements

- Tune model hyperparameters using cross-validation.
- Compare additional classification algorithms.
- Evaluate decision thresholds to balance churn recall and precision.
- Add explainability with SHAP.
- Build an interactive interface for customer-level churn predictions.
- Validate model performance on newer customer data.

## ⚠️ Limitations

- The dataset represents a particular telecom customer population and may not generalize to every provider.
- Feature importance indicates model reliance, not causation.
- Churn predictions are estimates and should support—not replace—business judgement.
- Model performance can change when customer behaviour or service offerings change.

## 👤 Author

**Lav Bhatia**  
Computer Science & Information Technology

---

<div align="center">

**If you find this project useful, consider giving the repository a ⭐**

Made with Python and Machine Learning.

</div>
