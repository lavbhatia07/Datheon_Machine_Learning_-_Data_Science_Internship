
<div align="center">

# 💬 NLP Sentiment Classification

### Customer Review Analysis Using TF-IDF and Machine Learning

Turn written customer feedback into meaningful sentiment predictions with Natural Language Processing.

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![NLP](https://img.shields.io/badge/Domain-NLP-8A2BE2?style=for-the-badge)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine_Learning-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen?style=for-the-badge)

</div>

---

## ✨ About the Project

Customer reviews contain valuable opinions about products and services. Manually reading and categorizing every review can be time-consuming.

**NLP Sentiment Classification** demonstrates how Natural Language Processing and machine learning can automatically classify review text as **positive** or **negative**.

The project uses text preprocessing and **TF-IDF (Term Frequency–Inverse Document Frequency)** to convert review text into numerical features.

It trains and compares two machine learning algorithms:

- **Multinomial Naive Bayes**
- **Logistic Regression**

A prediction function is also provided to test the sentiment of new review text.

## 🎯 Objectives

- Inspect and clean the supplied customer-review dataset.
- Preprocess text by removing HTML tags, URLs, punctuation, and stopwords.
- Apply lemmatization to normalize words.
- Convert cleaned reviews into numerical features using TF-IDF.
- Train and compare Naive Bayes and Logistic Regression.
- Evaluate predictions using classification metrics and a confusion matrix.
- Predict sentiment for custom user-entered reviews.

## 📁 Dataset

The project uses the supplied file: **`sentiment_reviews.csv`**.

The dataset contains these columns:

| Column | Description |
|---|---|
| `review_id` | Identifier for each review |
| `review_text` | Customer review text used as model input |
| `sentiment` | Sentiment label encoded numerically |

### Target Labels

| Value | Meaning |
|---|---|
| 0 | Negative |
| 1 | Positive |

### Dataset Cleaning

The supplied dataset contains **10 original rows**. One row has a missing sentiment value and is removed during cleaning.

The resulting dataset contains **9 usable reviews**:

- 5 positive reviews
- 4 negative reviews

The `review_id` column is an identifier and is not used as a model feature.

> **Dataset limitation:** This is a very small dataset. It is suitable for demonstrating the NLP workflow, but not for building or validating a reliable real-world sentiment classifier.

## 🧰 Tech Stack

| Area | Libraries / Tools |
|---|---|
| Programming language | Python |
| Data handling | Pandas, NumPy |
| Text processing | NLTK, Regular Expressions |
| Feature extraction | Scikit-learn TF-IDF |
| Machine learning | Multinomial Naive Bayes, Logistic Regression |
| Visualization | Matplotlib, Seaborn |
| Model persistence | Joblib |
| Environment | Jupyter Notebook |

## 🔄 Workflow

```text
          Customer Review Dataset
                    |
                    v
             Data Inspection
                    |
                    v
              Data Cleaning
       - Handle missing values
       - Normalize sentiment labels
       - Exclude review identifier
                    |
                    v
            Text Preprocessing
       - Remove HTML tags and URLs
       - Convert to lowercase
       - Remove punctuation
       - Remove stopwords
       - Lemmatization
                    |
                    v
              Train / Test Split
                    |
                    v
             TF-IDF Vectorization
                    |
                    v
              Model Training
             +------+------+
             |             |
             v             v
        Naive Bayes   Logistic Regression
             |             |
             +------+------+
                    |
                    v
               Evaluation
       - Accuracy, Precision, Recall
       - F1-score and Confusion Matrix
                    |
                    v
          Custom Sentiment Prediction
```

## 🧹 Text Preprocessing

The review text is cleaned before feature extraction:

1. **HTML decoding and removal:** Decodes HTML entities and removes HTML tags.
2. **URL removal:** Removes web links from review text.
3. **Lowercasing:** Converts text to lowercase for consistent processing.
4. **Punctuation and number removal:** Keeps alphabetic text.
5. **Tokenization:** Splits text into individual words.
6. **Stopword removal:** Removes common English words using NLTK.
7. **Lemmatization:** Converts words to their base form using `WordNetLemmatizer`.

## 🔢 TF-IDF Feature Extraction

TF-IDF converts cleaned review text into numerical feature vectors that machine learning algorithms can process.

The project uses `TfidfVectorizer` with a maximum vocabulary size of **5,000 features**.

The vectorizer is fitted on the training reviews and then used to transform the test reviews. This prevents the test set from influencing vocabulary fitting.

## 🤖 Models

### 1. Multinomial Naive Bayes

Multinomial Naive Bayes is a probabilistic classification algorithm commonly used for text classification. It estimates the likelihood of a sentiment class based on the words present in a review.

### 2. Logistic Regression

Logistic Regression is a supervised classification algorithm that estimates the probability of a review belonging to a sentiment class. It is included as a comparison model.

The model with the better observed test accuracy is selected for the notebook's custom prediction function.

## 📊 Evaluation

The notebook evaluates both classifiers using:

| Metric | What it measures |
|---|---|
| Accuracy | Overall proportion of correct predictions |
| Precision | Proportion of predicted positive cases that are correct |
| Recall | Proportion of actual positive cases identified |
| F1-score | Balance between precision and recall |
| Confusion matrix | Correct and incorrect predictions by class |

It also visualizes model accuracy and confusion matrices.

> **Important:** Because only 9 reviews remain after cleaning, the evaluation set is extremely small. Do not interpret the resulting scores as reliable estimates of performance on unseen customer reviews.

## 🧪 Try a Custom Review

The notebook includes a `predict_sentiment()` function that accepts a review and returns the predicted sentiment and model confidence.

Example:

```python
review = "The product quality is excellent and I really love it."

result = predict_sentiment(review)

print(result)
```

The numeric prediction represents:

- `1` = Positive
- `0` = Negative

The actual prediction and confidence depend on the trained model.

## 📂 Repository Structure

```text
NLP-Sentiment-Classification/
|
|-- sentiment_reviews.csv
|-- nlp_sentiment_classification.ipynb
|-- sentiment_model.pkl
|-- tfidf_vectorizer.pkl
|-- requirements.txt
|-- README.md
```

The `.pkl` files are generated after running the notebook's model-saving cell.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/lavbhatia07/Datheon_Machine_Learning_-_Data_Science_Internship.git
cd <your-repository>
```

### 2. Create a virtual environment

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

### 4. Keep the dataset in the project folder

Make sure `sentiment_reviews.csv` is in the same directory as the notebook.

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `nlp_sentiment_classification.ipynb` and run the cells in order.

## 📦 Requirements

The project uses the following Python packages:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
nltk
joblib
jupyter
ipykernel
```

## 🔮 Future Improvements

- Collect a substantially larger and more diverse labeled review dataset.
- Use a stratified train-test split with enough examples in each class.
- Apply cross-validation for more dependable model comparison.
- Experiment with n-grams and TF-IDF parameters.
- Tune model hyperparameters.
- Add neutral sentiment if sufficient labeled examples become available.
- Build a simple web interface for live sentiment prediction.
- Explore advanced NLP models such as word embeddings or transformer-based classifiers.

## ⚠️ Limitations

- The supplied dataset is very small (9 usable records after cleaning).
- The model can easily overfit and may not generalize to new reviews.
- A tiny test set makes accuracy, precision, recall, and F1-score unstable.
- The current target labels support binary sentiment classification only: positive and negative.
- Model confidence is not a guarantee that a prediction is correct.

## 👨‍💻 Author

**Lav Bhatia**  
Computer Science & Information Technology

---

<div align="center">

### ⭐ If you find this project useful, consider starring the repository!

**Built with Python, NLP, and Machine Learning.**

</div>
