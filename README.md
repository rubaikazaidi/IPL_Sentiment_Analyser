# IPL Sentiment Classification

## Objective

Classify IPL-related tweets into sentiment categories using classical machine learning approaches.

## Dataset

Training Dataset:
- 300R IPL Indian English Sentiment Dataset

Test Dataset:
- 80R IPL Sentiment Dataset

## Models Evaluated

1. CountVectorizer + Multinomial Naive Bayes
2. TF-IDF + Logistic Regression
3. TF-IDF + Linear SVC
4. Character N-gram TF-IDF + Linear SVC
5. Hashing Vectorizer + SGD Classifier

## Results

| Model | Accuracy | Macro F1 |
|---------|---------|---------|
| Count_NB | 0.6875 | 0.6734 |
| CHAR_SVC | 0.6875 | 0.6655 |
| TFIDF_SVC | 0.6250 | 0.6405 |
| HASH_SGD | 0.5625 | 0.5613 |
| TFIDF_LR | 0.4375 | 0.4545 |

## Best Model

CountVectorizer + Multinomial Naive Bayes

Accuracy: 68.75%

Macro F1: 0.6734

## Files

- notebook.ipynb
- results_80R.csv
- best_model.pkl
- README.md