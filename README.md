# Bert-Based Sentiment Classifier for Book Reviews

## Project Task
The goal of this project was to build a sentiment analysis model that classifies book reviews into three categories: Recommmended, Not recommended, and Neutral. This falls under the NLP task of text classification (specifically, multi-class sentiment classification).

## Dataset
The dataset was sourced from Kaggle: Book Review Dataset for Sentiment Analysis. It contains thousands of user-generated book reviews labeled with sentiment categories.
The original dataset showed a significant class imbalance, with the Neutral class underrepresented. This was addressed by:

Balancing the dataset through undersampling of majority classes

Applying class weights during training to penalize misclassification of minority classes

📎 Book Review Dataset for Sentiment Analysis on Kaggle

## Pre-trained Model
I fine-tuned the bert-base-uncased model from Hugging Face Transformers. This model was selected because:

It’s a general-purpose English language model pre-trained on BooksCorpus and Wikipedia

It has strong performance across a wide range of NLP tasks

It supports easy fine-tuning for classification tasks

## Performance Metrics
| Class     | Precision | Recall | F1-score | Support |
|-----------|-----------|--------|----------|---------|
| Negative  | 1.00      | 0.98   | 0.99     | 144     |
| Positive  | 1.00      | 1.00   | 1.00     | 139     |
| Neutral   | 0.98      | 1.00   | 0.99     | 149     |
| **Accuracy** |         |        | **0.99** | 432     |
| **Macro Avg** | 0.99   | 0.99   | 0.99     | 432     |
| **Weighted Avg** | 0.99 | 0.99 | 0.99     | 432     |

It successfully overcame early issues with class imbalance, especially for the Neutral class.

## Final Classification Report Summary

The model achieved 99% overall accuracy, with near-perfect precision and recall across all classes.

The Neutral class, which was previously underrepresented and misclassified, now shows perfect recall and high precision, thanks to class balancing and weighted loss.

The confusion matrix confirms that the model makes very few errors and shows no systematic bias toward any class.

This performance indicates that the model is well-optimized, generalizes effectively, and is ready for deployment in real-world applications.


## Hyperparameters
class weights: used to address class imbalance and improve Neutral class performance

