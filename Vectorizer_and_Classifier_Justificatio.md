# Vectorizer and Classifier Justification

# Introduction

The goal of this project is to classify IPL-related tweets into sentiment categories using machine learning techniques. Since machine learning models cannot process raw text directly, the text must first be converted into numerical representations using vectorization techniques. Different classifiers are then trained on these vectorized representations to determine which combination produces the best sentiment classification performance.

---

# Vectorization Techniques Evaluated

# 1. CountVectorizer

CountVectorizer transforms text into a matrix of token frequencies. Each unique word in the dataset becomes a feature, and the value of each feature corresponds to the number of times that word appears in a tweet.

Example:

Tweet:
"great batting today"

Features:

| Word    | Count |
| ------- | ----- |
| great   | 1     |
| batting | 1     |
| today   | 1     |

Advantages:

* Simple and computationally efficient.
* Preserves important word frequency information.
* Performs well on short text datasets such as tweets.
* Easy to interpret.

---

# 2. TF-IDF Vectorizer

Term Frequency–Inverse Document Frequency (TF-IDF) assigns weights to words based on their importance within the dataset.

Frequently occurring words receive lower weights, while informative words receive higher weights.

Advantages:

* Reduces the influence of very common words.
* Highlights discriminative terms.
* Often improves performance for text classification tasks.

---

# 3. Character-Level TF-IDF

Instead of representing complete words, character-level TF-IDF represents sequences of characters (n-grams).

Example:

Word:
"cricket"

Character trigrams:

* cri
* ric
* ick
* cke
* ket

Advantages:

* Handles spelling mistakes and abbreviations.
* Captures patterns commonly found in social media text.
* More robust to informal language.

---

# 4. Hashing Vectorizer

HashingVectorizer converts tokens into fixed-length feature vectors using a hashing function.

Advantages:

* Memory efficient.
* Scales well to large datasets.
* Does not require storing a vocabulary.

Disadvantages:

* Feature interpretation is difficult.
* Hash collisions may occur.

---

# Classification Algorithms Evaluated

# 1. Multinomial Naive Bayes

Multinomial Naive Bayes is a probabilistic classifier designed specifically for text classification tasks.

It assumes that word occurrences are conditionally independent and estimates class probabilities based on word frequencies.

Advantages:

* Extremely fast training and prediction.
* Effective for sparse text features.
* Strong baseline for sentiment analysis.
* Performs well with small datasets.

---

# 2. Logistic Regression

Logistic Regression is a linear classification algorithm that predicts the probability of a tweet belonging to a particular sentiment class.

Advantages:

* Interpretable model.
* Effective for high-dimensional text data.
* Produces probabilistic outputs.

---

# 3. Linear Support Vector Classifier (Linear SVC)

Linear SVC attempts to find the optimal decision boundary that separates sentiment classes.

Advantages:

* Strong performance in text classification tasks.
* Handles high-dimensional feature spaces efficiently.
* Robust against overfitting.

---

# 4. SGD Classifier

The Stochastic Gradient Descent (SGD) classifier is an efficient linear model trained using incremental optimization.

Advantages:

* Fast training.
* Suitable for large-scale text datasets.
* Low memory requirements.

---

# Experimental Results

The following vectorizer-classifier combinations were evaluated:

| Model                                     | Accuracy | Macro F1 |
| ----------------------------------------- | -------- | -------- |
| CountVectorizer + Multinomial Naive Bayes | 0.6875   | 0.6734   |
| Character TF-IDF + Linear SVC             | 0.6875   | 0.6655   |
| TF-IDF + Linear SVC                       | 0.6250   | 0.6405   |
| Hashing Vectorizer + SGD Classifier       | 0.5625   | 0.5613   |
| TF-IDF + Logistic Regression              | 0.4375   | 0.4545   |

---

# Selected Model

The CountVectorizer + Multinomial Naive Bayes combination achieved the highest Macro F1 score (0.6734) while also achieving the highest accuracy (68.75%).

This combination was selected as the final model because:

1. It produced the best overall classification performance.
2. It handled the short tweet-based dataset effectively.
3. It is computationally efficient and easy to train.
4. It performed better than more complex alternatives on the provided dataset.

---

# Conclusion

Multiple vectorization and classification techniques were evaluated for IPL tweet sentiment analysis. The experimental results demonstrate that CountVectorizer combined with Multinomial Naive Bayes provides the most effective balance of accuracy and generalization on the given dataset. Therefore, this combination was selected as the final model for deployment and evaluation.
