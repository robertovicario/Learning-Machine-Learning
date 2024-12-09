# Maximum Likelihood Classification

## Overview

_Maximum Likelihood Classification_ is a method used to classify data points into categories based on probability.

The _Core Idea_ is to find the category that is most likely (has the highest probability) for a given data point.

Even this method builds upon _Bayes' Theorem_ (general formula).

## Sigmoid Function

This function takes any real number and maps it to a value between 0 and 1:

$$
S(x) = \frac{1}{1 + e^{-x}}
$$

Where:

- If $x$ is very large (positive), $S(x)$ approaches 1.
- If $x$ is very small (negative), $S(x)$ approaches 0.
- At $x = 0$, $S(x) = 0.5$.

## Logistic Regression

1. Takes input features and combines them into a single value using a linear equation:

   $$
   z = w_1x_1 + w_2x_2 + \ldots + w_nx_n + b
   $$

   where:

   - $x_1, x_2, \ldots, x_n$: Input features.
   - $w_1, w_2, \ldots, w_n$: Weights (parameters to learn).
   - $b$: Bias term.

2. Passes $z$ through the **sigmoid function** to get a probability:

   $$
   P(Y = 1 | X) = \frac{1}{1 + e^{-z}}
   $$

3. Compares this probability to a threshold (e.g., 0.5) to decide the class.

### Summary

| **Classifier** | **Pros** | **Cons** | **Use-Case** |
| - | - | - | - |
| Logistic Regression | Computationally efficient for small to medium-sized datasets. | Sensitive to outliers, requires careful feature scaling for optimal performance. | Spam Detection, Credit Scoring, Medical Diagnosis |
