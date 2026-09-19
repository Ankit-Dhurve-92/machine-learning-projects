# Fake News Prediction using NLP and Machine Learning

## Overview

This project develops a machine learning-based text classification system to classify news articles as **Fake** or **Real**.

The project uses Natural Language Processing (NLP) techniques to convert news text into numerical features using TF-IDF and then applies Logistic Regression for classification.

## Dataset

The project uses the **WELFake Dataset**, which contains news articles labeled as fake or real.

Target labels:

- `0` - Fake News
- `1` - Real News

For computational efficiency, a balanced subset containing:

- 10,000 fake news samples
- 10,000 real news samples

was used for model training.

The dataset is included in this repository as:

`WELFake_Dataset.csv`

Dataset source:

https://www.kaggle.com/datasets/saurabhshahane/fake-news-classification

## Machine Learning Approach

The project follows the following workflow:

1. Load and inspect the dataset
2. Analyze the target distribution
3. Handle missing values
4. Combine news title and article text
5. Clean and normalize text
6. Perform exploratory data analysis
7. Create train-test split
8. Convert text into TF-IDF features
9. Train Logistic Regression classifier
10. Evaluate the model
11. Build a news prediction function

## Text Preprocessing

The text preprocessing pipeline includes:

- Lowercasing
- URL removal
- HTML tag removal
- Removal of unnecessary characters
- Whitespace normalization
- Combining title and article text

Additional text-length features were also analyzed during exploratory data analysis.

## TF-IDF Vectorization

**Term Frequency-Inverse Document Frequency (TF-IDF)** was used to convert news articles into numerical feature vectors.

The vectorizer uses:

- Maximum 50,000 features
- Unigrams and bigrams
- English stop-word removal
- Minimum document frequency of 2

TF-IDF gives higher importance to words that are useful for distinguishing between fake and real news while reducing the importance of very common words.

## Model

A **Logistic Regression** classifier was trained on the TF-IDF representation of the news content.

The complete preprocessing and classification workflow was implemented using a Scikit-learn `Pipeline`.

```text
News Title + Text
        ↓
   Text Cleaning
        ↓
    TF-IDF
        ↓
Logistic Regression
        ↓
 Fake / Real
