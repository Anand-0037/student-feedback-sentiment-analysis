# student-feedback-sentiment-analysis

This project analyzes student feedback on teaching, course content, examinations, lab work, library facilities, and extracurricular activities. The aim is to classify the sentiment of feedback into **positive, neutral, or negative** using Natural Language Processing (NLP) and Machine Learning.

---
## Project Workflow

## 1\. Dataset

* Source: Kaggle – [Student Feedback Dataset](https://www.kaggle.com/datasets/brarajit18/student-feedback-dataset)
* Size: 185 rows × 12 columns
* Categories: teaching, course content, examination, lab work, library facilities, extracurricular

## 2\. Preprocessing

* Text cleaning (lowercasing, removing punctuation, lemmatization)
* Custom stopword removal (keeping opinion words like _good, bad, excellent, poor_)
* Handling missing values

## 3\. Exploratory Data Analysis (EDA)

* Sentiment distribution visualizations (pie charts by category)
* Overall sentiment breakdown:  
   * Positive: \~74%  
   * Neutral: \~14%  
   * Negative: \~13%
* Common words per sentiment group

## 4\. Modeling

* Features extracted using **TF-IDF (1–3 n-grams, 1500 max features)**
* Models trained:  
   * Naive Bayes → Accuracy: 0.757  
   * Random Forest (balanced) → Accuracy: 0.811 (best model)

## 5\. Feature Importance

* Top words influencing predictions visualized via feature importance scores

## 6\. Predictions

* Function `predict_sentiment()` classifies custom feedback with confidence score
* Example:  
   * _“The teaching is excellent and very interactive” → Positive (96% confidence)_

---

## Results

* **Random Forest** outperformed Naive Bayes with \~81% accuracy
* Dataset is **imbalanced (Positive-heavy)** → possible improvement with SMOTE/oversampling

---

## scope of improvemnt

* Apply **SMOTE** or class-weight tuning for balance
* Experiment with **deep learning (LSTMs, BERT)** for better predictions
* Expanding the dataset

---

## Requirements

Install dependencies:

bash

`pip install pandas numpy matplotlib seaborn scikit-learn nltk textblob
`

---

## Usage

Run all steps: preprocessing → EDA → training → predictions.

python

`result = predict_sentiment("Poor quality, needs improvement")
print(result)`
