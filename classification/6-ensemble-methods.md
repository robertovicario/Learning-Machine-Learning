# Ensemble Methods

## Overview

_Ensemble Methods_ are techniques that combine multiple individual models to produce a stronger, more accurate prediction than any single model.

The _Core Idea_ is that by combining different models, their individual weaknesses can be canceled out, and their collective strengths can provide better results.

## General Formula

In general, the prediction of an ensemble model can be expressed as:

$$
\hat{y} = \frac{1}{N} \sum_{i=1}^{N} h_i(x)
$$

where:

- $\hat{y}$ determines the final prediction.
- $N$ is the number of models in the ensemble.
- $h_i(x)$ determines the prediction from each model $i$ for the input data $x$.

## Ensemble Methods

### Bagging (Bootstrap Aggregating)

Bagging involves creating multiple copies of the dataset using _Bootstrapping_ (random sampling with replacement), and training a separate model on each dataset

The final prediction is made by _Averaging_ (for regression) or _Majority Voting_ (for classification) the predictions from all models.

### Boosting

Boosting focuses on training models sequentially, where each new model corrects the errors made by the previous ones.

The final prediction is a weighted sum of the predictions from all models, giving more weight to models that perform well.

### Stacking

Stacking combines predictions from several models by training a meta-model (called the stacker) on the outputs of the base models. 

Each base model is trained independently, and the meta-model learns how to best combine their predictions.

### Blending

Similar to stacking, blending also combines the predictions of different models. However, blending uses a validation set (instead of cross-validation like stacking) to train the meta-model.

### Summary

| **Method** | **Pros** | **Cons** |
| - | - | - |
| Bagging | Reduces variance and overfitting | Doesn’t reduce bias much |
| Boosting | Reduces both bias and variance | Prone to overfitting if not tuned |
| Stacking | Combines multiple diverse models for better predictions | Can be complex to implement and requires careful meta-model selection |
| Blending | Simpler and faster alternative to stacking | Less effective for complex data compared to stacking |

## Classifiers Based on Ensemble Methods

### Random Forests

1. Split the data into training and testing sets.
2. Create multiple bootstrap samples (random subsets of the data with replacement).
3. For each sample, train a decision tree on a subset of the features (random feature selection at each split).
4. For classification, use _Majority Voting_ across all trees. For regression, _Average_ the predictions from all trees.
5. Measure performance on test data.

### AdaBoost

1. Start by giving equal weight to all data points.
2. Train a weak classifier (like a decision tree with a single split) on the data.
3. Increase the weights of the misclassified data points so that the next classifier focuses more on them.
4. Repeat this process for a specified number of rounds or until the model is sufficiently accurate.
5. Combine the predictions of all classifiers, giving more weight to classifiers that performed well.

### Pros & Cons

| **Classifier** | **Method** | **Pros** | **Cons** |
| - | - | - | - | - |
| Random Forest | Bagging | Reduces overfitting and handles large datasets well | Slower to predict as it aggregates many trees |
| AdaBoost | Boosting | Boosts weak models and reduces both bias and variance | Can overfit if not tuned |
