# 🏡 Housing Price Prediction

<p align="center">
  <b>Machine Learning-Based House Price Prediction System</b><br>
  Predicting housing prices using data analysis, regression algorithms, and model evaluation.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python" />
  <img src="https://img.shields.io/badge/Machine%20Learning-Regression-orange" />
  <img src="https://img.shields.io/badge/Library-Scikit--Learn-F7931E?logo=scikitlearn" />
  <img src="https://img.shields.io/badge/Data%20Analysis-Pandas-150458?logo=pandas" />
  <img src="https://img.shields.io/badge/Status-Completed-success" />
</p>

---

## 📌 Overview

**Housing Price Prediction** is a Machine Learning project that aims to predict median house values using housing-related information.

The project uses the **California Housing Dataset** and applies regression techniques to understand relationships between housing features and property prices.

Multiple machine learning models are trained and evaluated to identify the best-performing model based on prediction error metrics, particularly **Root Mean Squared Error (RMSE)**.

The primary objective is to build a reliable regression pipeline while understanding the complete machine learning workflow, from data preprocessing to model evaluation.

## 🎯 Project Objectives

- Understand and analyze housing data.
- Perform Exploratory Data Analysis (EDA).
- Handle missing values and prepare data for model training.
- Identify important features influencing house prices.
- Implement and compare multiple regression algorithms.
- Evaluate model performance using regression metrics.
- Select the best-performing model based on RMSE.

## 📊 Dataset

**Dataset:** California Housing Dataset

The dataset contains information about housing districts in California.

| Attribute | Description |
|---|---|
| Longitude | Geographic longitude |
| Latitude | Geographic latitude |
| Housing Median Age | Median age of houses |
| Total Rooms | Total number of rooms |
| Total Bedrooms | Total number of bedrooms |
| Population | Total population |
| Households | Number of households |
| Median Income | Median income of households |
| Median House Value | Target variable |
| Ocean Proximity | Location relative to the ocean |

**Dataset Statistics:**

- Total Records: 20,640
- Total Features: 9 input features
- Target Variable: `median_house_value`
- Problem Type: Supervised Machine Learning
- Learning Task: Regression

## ⚙️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | Machine learning algorithms and evaluation |
| Jupyter Notebook | Development environment |

## 🔄 Project Workflow

1. **Data Collection** – Load the California Housing Dataset.
2. **Data Understanding** – Explore dataset structure, columns, and data types.
3. **Data Cleaning** – Identify and handle missing values.
4. **Exploratory Data Analysis** – Analyze distributions, correlations, and feature relationships.
5. **Data Preprocessing** – Prepare numerical and categorical features for training.
6. **Model Training** – Train regression models.
7. **Model Evaluation** – Compare models using regression performance metrics.
8. **Model Selection** – Identify the model with the lowest RMSE.

## 🤖 Machine Learning Approach

This project follows a supervised regression approach.

The models are evaluated using the following metrics:

| Metric | Purpose |
|---|---|
| MAE | Measures average absolute prediction error |
| MSE | Measures average squared prediction error |
| RMSE | Measures prediction error in the target variable's units |
| R² Score | Measures the proportion of variance explained by the model |

### 🏆 Best Model Selection

The best-performing model is selected using the minimum RMSE value.

```python
best_model_name = results_df["RMSE"].idxmin()

print("Best Performing Model:", best_model_name)

print("\nPerformance:")
display(
    results_df.loc[[best_model_name]].round(4)
)
```

A lower RMSE indicates better predictive performance on the evaluated dataset.

## 📁 Project Structure

```text
Housing_Price_Prediction/
│
├── dataset/
│   └── california_housing.csv
│
├── notebooks/
│   └── housing_price_prediction.ipynb
│
├── README.md
│
└── requirements.txt
```

*Adjust the folder and file names above to match your actual repository structure.*

## 🚀 Getting Started

Follow these steps to run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Housing_Price_Prediction.git
```

### 2. Navigate to the Project Directory

```bash
cd Housing_Price_Prediction
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

If you do not have a requirements file yet, install the libraries using:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the project notebook and run the cells sequentially.

## 📈 Key Learning Outcomes

- Practical understanding of regression-based machine learning.
- Data preprocessing and feature engineering.
- Exploratory Data Analysis and data visualization.
- Training and comparing different regression models.
- Understanding MAE, MSE, RMSE, and R² metrics.
- Selecting an appropriate model based on evaluation results.

## 🔮 Future Improvements

- Develop an interactive web application for house price predictions.
- Build a user-friendly interface using Flask or Streamlit.
- Perform hyperparameter tuning to improve model performance.
- Apply feature importance analysis.
- Deploy the trained model using a cloud platform.

## 👨‍💻 Author

**Lav Bhatia**

Computer Science & Information Technology Student

Interested in Machine Learning, Data Science, and Artificial Intelligence.

- GitHub: [Your GitHub Profile](https://github.com/your-username)
- LinkedIn: [Your LinkedIn Profile](https://www.linkedin.com/)

---

<p align="center">
  <b>⭐ If you find this project useful, consider giving it a star!</b>
  <br><br>
  Made with ❤️ using Python and Machine Learning.
</p>
