# Error Analysis

Several prediction errors were observed during evaluation.

## Common Causes

### Ambiguous Sentiment

Some tweets contained both positive and negative expressions.

Example:

"Great batting but poor bowling today."

### Informal Language

IPL tweets frequently contain slang, abbreviations, and spelling variations.

### Sarcasm

Sarcastic tweets are difficult for traditional machine learning models to classify correctly.

Example:

"Fantastic performance... not."

### Limited Training Data

The 300-sample training dataset restricts the model's ability to learn rare sentiment patterns.

## Future Improvements

- Use larger datasets
- Apply transformer-based models such as BERT
- Incorporate emoji and hashtag features
- Perform hyperparameter optimization