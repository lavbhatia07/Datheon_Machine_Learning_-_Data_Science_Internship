<div align="center">

# 🌸 Iris Classification Benchmark

### A Multi-Class Machine Learning Pipeline with Scikit-learn

**Train. Evaluate. Compare. Understand.**

A clean, end-to-end classification project that benchmarks **Logistic Regression** and **Decision Tree** models on the Iris flower dataset.

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2EA44F?style=for-the-badge)

</div>

---

## 📌 Project Overview

This project demonstrates a complete **supervised multi-class classification workflow** using the Iris dataset. It explores the data, prepares the features, trains two machine-learning algorithms, and compares their performance using standard classification metrics and visualizations.

The goal is not just to train a model, but to understand how preprocessing, model choice, and evaluation work together in a reproducible machine-learning pipeline.

> **Project type:** Machine Learning · Supervised Learning · Multi-Class Classification

## 🎯 Objectives

- Explore the Iris dataset and understand its feature distributions.
- Inspect data quality, missing values, duplicates, and class balance.
- Split the data into training and testing sets using an **80:20 ratio**.
- Apply feature standardization with `StandardScaler`.
- Train and compare Logistic Regression and Decision Tree classifiers.
- Evaluate performance using accuracy, precision, recall, and F1-score.
- Visualize feature relationships, model performance, and confusion matrices.

## 🌼 Dataset

The project uses `iris_dataset.csv`, containing **150 flower samples** across three species.

| Feature | Description |
|---|---|
| `sepal_length` | Sepal length in centimeters |
| `sepal_width` | Sepal width in centimeters |
| `petal_length` | Petal length in centimeters |
| `petal_width` | Petal width in centimeters |
| `species` | Target class to predict |

### Target classes

- `setosa`
- `versicolor`
- `virginica`

The four measurements are the input features (`X`), while `species` is the target (`y`).

## 🧠 Models Benchmarked

| Model | How it works | Why include it? |
|---|---|---|
| **Logistic Regression** | Learns class decision boundaries from a linear model | A strong, interpretable baseline for classification |
| **Decision Tree** | Learns a sequence of feature-based decision rules | Captures nonlinear patterns and is easy to visualize |

Both models use the same training/testing split for a fair comparison. The workflow uses a Scikit-learn `Pipeline` so preprocessing is fitted on the training data and then applied to the test data without data leakage. Feature scaling is particularly useful for Logistic Regression; it is not strictly necessary for Decision Trees, but is retained here to keep the pipeline consistent.

## ⚙️ Workflow

```text
              ┌─────────────────────┐
              │   Load Iris CSV     │
              └──────────┬──────────┘
                         ▼
              ┌─────────────────────┐
              │ Explore & Validate  │
              │   the Dataset       │
              └──────────┬──────────┘
                         ▼
              ┌─────────────────────┐
              │ Train/Test Split    │
              │       80 / 20       │
              └──────────┬──────────┘
                         ▼
              ┌─────────────────────┐
              │ Standardize Features│
              │   StandardScaler    │
              └──────────┬──────────┘
                         ▼
                ┌────────┴────────┐
                ▼                 ▼
       ┌────────────────┐ ┌────────────────┐
       │ Logistic       │ │ Decision       │
       │ Regression     │ │ Tree           │
       └───────┬────────┘ └───────┬────────┘
               └────────┬────────┘
                        ▼
              ┌─────────────────────┐
              │ Evaluate & Compare  │
              │ Metrics + Plots     │
              └─────────────────────┘
```

## 📊 Evaluation Metrics

The notebook reports the following metrics for both models:

| Metric | What it tells us |
|---|---|
| **Accuracy** | Fraction of all test samples predicted correctly |
| **Precision (Macro)** | Average precision across classes, with each class weighted equally |
| **Recall (Macro)** | Average recall across classes, with each class weighted equally |
| **F1-score (Macro)** | Average class-wise F1-score, giving each class equal weight |
| **Confusion Matrix** | Shows correct predictions and which classes are confused |

Macro-averaging is used for precision, recall, and F1-score so each species contributes equally to the overall score.

## 📈 Visualizations

The notebook generates:

- **Species distribution plot** — checks the number of samples per class.
- **Correlation heatmap** — explores correlations between numerical features.
- **Pairplot** — compares feature relationships across the three species.
- **Confusion matrix heatmaps** — shows class-wise prediction performance.
- **Model comparison chart** — compares the four evaluation metrics.
- **Decision tree plot** — visualizes the learned decision rules.

> Visualizations and metric values are generated when you run the notebook. No benchmark scores are hard-coded in this README.

## 🗂️ Repository Structure

```text
Iris-Classification-Benchmark/
├── classification_benchmark.ipynb   # Main notebook: code, metrics, and plots
├── iris_dataset.csv                  # Dataset used by the notebook
├── requirements.txt                  # Python dependencies
└── README.md                         # Project documentation
```

If you place the notebook and CSV in a subfolder, update the CSV path in the notebook accordingly.

## 🚀 Getting Started

### 1. Clone the repository

Replace the placeholder with your public GitHub repository URL:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

### 2. Create and activate a virtual environment (recommended)

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

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `classification_benchmark.ipynb` and run the cells from top to bottom.

## 📦 Requirements

Create a `requirements.txt` file with:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter
ipykernel
```

Python **3.10 or newer** is recommended.

## 🔍 How to Interpret the Results

After executing the notebook:

1. Compare both models in the benchmark results table.
2. Check macro precision, recall, and F1-score instead of relying on accuracy alone.
3. Inspect the confusion matrices to see whether errors are concentrated in a particular species.
4. Review the decision tree to understand its learned rules.
5. Identify the best model based on the metric you choose. This notebook uses **macro F1-score** for its final model selection.

The best-performing model should be reported based on the actual results from your run; results can vary with the split and model settings.

## 🛠️ Tech Stack

- **Python** — core programming language
- **Pandas & NumPy** — data handling and numerical operations
- **Matplotlib & Seaborn** — visual analysis and plotting
- **Scikit-learn** — preprocessing, model training, and evaluation
- **Jupyter Notebook** — interactive development and reporting

## 💡 Key Learnings

- Building a reproducible machine-learning workflow.
- Separating input features from the target variable.
- Using stratified train/test splitting for multi-class classification.
- Preventing preprocessing data leakage with pipelines.
- Comparing models with multiple evaluation metrics.
- Interpreting confusion matrices and exploratory visualizations.

## 🔮 Possible Improvements

- Add cross-validation for more reliable performance estimates.
- Tune model hyperparameters with `GridSearchCV`.
- Compare additional classifiers such as K-Nearest Neighbors and Support Vector Machines.
- Add a 2D decision-boundary plot using two selected features.
- Save the trained pipeline and demonstrate predictions on new flower measurements.

## 👤 Author

**Lav Bhatia**  
Computer Science & Information Technology student

> Update this section with your GitHub profile and LinkedIn profile links before publishing, if desired.

## 📄 License

This project is intended for educational and portfolio purposes. Add a license file if you want to specify reuse and distribution terms.

---

<div align="center">

**Built with Python and Scikit-learn 🌱**

*Learning machine learning one experiment at a time.*

</div>
