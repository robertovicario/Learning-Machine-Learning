# Bayesian Classification

## Overview

_Bayesian classification_ is a probabilistic approach used to classify data into different categories.

The _Core Idea_ is based on _Bayes' Theorem_, which provides a way to update probabilities as new information is obtained.

## General Formula (Bayes' Theorem)

Let $A$ and $B$ be two events, with $P(B) > 0$. Then, Bayes' Theorem states:

$$
P(A \mid B) = \frac{P(B \mid A) P(A)}{P(B)}
$$

Where:

- $P(A \mid B)$ is the _Posterior Probability_: the probability of event $A$ occurring given that $B$ has occurred.
- $P(B \mid A)$ is the _Likelihood_: the probability of event $B$ occurring given that $A$ has occurred.
- $P(A)$ is the _Prior Probability_: the initial probability of event $A$ before considering the evidence $B$.
- $P(B)$ is the _Marginal Probability_ of event $B$, which can be computed using the _Law of Total Probability_.

## Bayesian Models

### Naïve Bayes

1. Calculate the prior probability $P(C)$ for each class.
2. Calculate the likelihood $P(x_i|C)$ for each feature $x_i$ given each class.
3. Multiply these probabilities for all features and combine with the prior to compute $P(C|X)$.
4. Choose the class with the highest posterior probability.

### Bayesian Networks

**Key Components:**

- **Nodes:** Represent variables (features and classes).
- **Edges:** Show conditional dependencies between variables.
- **Conditional Probability Tables (CPTs):** Quantify the relationships.

**Steps:**

1. Construct the graph by identifying variables and their dependencies.
2. Specify conditional probabilities for each node given its parents.
3. Use the network to calculate posterior probabilities using _Bayes' Theorem_.

### Summary

| **Classifier** | **Pros** | **Cons** | **Use-Case** |
| - | - | - | - |
| Naïve Bayes | Simple, fast, works well with large datasets, easy to implement | Assumes features are independent (may not be true), struggles with correlated features | Text Classification, Spam Filtering, Sentiment Analysis |
| Bayesian Networks | Can handle complex dependencies, more accurate for complex problems | Requires more data and domain knowledge, computationally intensive | Risk Assessment, Gene Expression Analysis, Decision Support Systems |
