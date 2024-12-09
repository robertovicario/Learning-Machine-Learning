# Classification Trees

## Overview

_Classification Trees_ work by splitting the data into smaller subsets based on certain conditions, represented visually as a tree structure.

The _Core Idea_ of a classification tree is to divide the dataset into groups that are as pure as possible.

## Decision Tree Classifier

**Key Components:**

1. **Root Node:** Represents the entire dataset and is split into two or more homogeneous sets.
2. **Decision Nodes:** Intermediate nodes that represent a test on a feature.
3. **Leaf Nodes:** Terminal nodes that provide the final output.
4. **Splitting Criterion:** The metric used to determine the best split at each node (e.g., Gini Index, Entropy, Information Gain).

**Steps:**

1. **Choose a Splitting Criterion:** Select the feature and threshold to split the dataset in a way that maximizes purity.
2. **Split the Data:** Partition the dataset based on the chosen splitting criterion.
3. **Repeat Recursively:** Apply the same process to the resulting subsets to grow the tree.
4. **Stop Condition:** Stop splitting when one of the following is met:
   - All data in a subset belongs to a single class.
   - A pre-defined maximum tree depth is reached.
   - The number of samples in a node falls below a threshold.
5. **Pruning (optional):** Reduce the size of the tree to prevent overfitting by removing nodes that provide little predictive power.

### Pros & Cons

| **Classifier** | **Pros** | **Cons** |
| - | - | - |
| Decision Tree | Handles both numerical and categorical data. | May not generalize well to unseen data |
