# Distance Classification

## Overview

_Distance Classification_ is a method used to group or categorize data points based on how far they are from one another in a defined space.

The _Core Idea_ is to compare the distance of a given data point (input) to predefined reference points. Based on these distances, we assign the point to a specific group.

## General Formula

In general, for two points in $n$-dimensional space $P(x_1, x_2, \dots, x_n)$ and $Q(y_1, y_2, \dots, y_n)$, the generalized distance formula is:

$$
D(P, Q) = \left( \sum_{i=1}^n |x_i - y_i|^p \right)^{1/p}
$$

where $p$ determines the type of distance.

## Distance Metrics

### Euclidean Distance

Imagine measuring the shortest path between two points with a ruler. The straight-line distance between two points in space:

$$
D = \sqrt{\sum_{i=1}^n (x_i - y_i)^2}
$$

Works well when directions and true physical distances matter.

### Manhattan Distance

Think of walking on a grid-like city map where you can only move horizontally or vertically. The sum of absolute differences of their coordinates:

$$
D = \sum_{i=1}^n |x_i - y_i|
$$

Useful for grid-based systems or for high-dimensional spaces where diagonal distance is less relevant.

### Chebyshev Distance

Measures the longest one-step movement required to reach the point. The maximum absolute difference between coordinates:

$$
D = \max_{i=1}^n |x_i - y_i|
$$

Useful in games like chess, where only the farthest movement matters.

### Summary

| **Distance** | **Path Type** | **Use-Case** |
| - | - | - |
| Euclidean | Straight-line path | Clustering or real-world coordinates |
| Manhattan | Grid or stepwise path | City navigation, high-dimensional data|
| Chebyshev | Longest single move | Chess moves, warehouse logistics |

## Distance-Based Models

### Minimum Distance Classifier

1. Compute the centroid (mean position) for each class using the training data. For class $i$, the centroid is:

    $$
    C_i = \frac{1}{n_i} \sum_{j=1}^{n_i} P_j
    $$

    where $n_i$ is the number of points in class $i$, and $P_j$ are the points.

2. For a given input point $P$, calculate the distance to each centroid $C_i$ (e.g., using Euclidean distance).
3. Assign $P$ to the class with the smallest distance.

### Box Classifier

1. Define boundaries (min and max limits) for each feature in the dataset for each class. For class $i$, define ranges like $x_{\text{min}}, x_{\text{max}}, y_{\text{min}}, y_{\text{max}}$.
2. For a given input point $P(x, y)$: Check if $x$ and $y$ lie within the defined bounds of a specific box.
3. Assign $P$ to the class corresponding to the box it falls in.

### k-Nearest Neighbors (KNN)

1. Choose the value of $k$.
2. For a given input point $P$:
   - Compute the distance from $P$ to every point in the training dataset.
   - Sort the distances in ascending order.
3. Select the $k$ closest points.
4. Assign $P$ to the majority class among the $k$ neighbors.

### Summary

| **Classifier** | **Pros** | **Cons** | **Use-Case** |
| - | - | - | - |
| Minimum Distance | Simple and fast | Struggles with overlapping data | Customer segmentation,  Document Classification, Face Recognition |
| Box Classifier | Quick for fixed regions | Rigid, doesn't handle overlap well | Age/Income Groupings, Traffic Sign Detection, Object Detection |
| KNN | Flexible, handles complex data | Slow for large datasets | Image or Voice Classification, Recommendation Systems, Medical Diagnosis |
