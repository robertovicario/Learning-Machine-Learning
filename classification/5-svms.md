# Support Vector Machines (SVMs)

## Overview

_Support Vector Machines_ are powerful algorithms used for classification and regression tasks. They aim to find the best boundary, called a **Hyperplane**, that separates data points into different classes.

To simplify the _Core Idea_, imagine two groups of points scattered on a flat surface. Your goal is to draw a straight line that divides the groups in a way that leaves the most space between them. The points closest to the line, known as support vectors, are the key to defining its position. In three dimensions, this idea extends to a flat plane that separates the points.

## General Formula

The equation of a hyperplane in SVM can be written as:

$$
w \cdot x + b = 0
$$

where:

- $w$ is the weight vector (defines the orientation of the hyperplane).
- $x$ is the input vector (data point).
- $b$ is the bias term (defines the position of the hyperplane).

The objective of SVM is to solve this optimization problem:

$$
\text{Minimize: } \frac{1}{2} \|w\|^2
$$

$$
\text{Subject to: } y_i (w \cdot x_i + b) \geq 1, \, \forall i
$$

where $y_i$ represents the class label of data point $x_i$ (e.g., +1 or -1).

## Kernel Functions

A kernel function helps SVM handle cases where the data is not linearly separable by transforming the data into a higher-dimensional space where a hyperplane can separate the classes.

It allows SVM to perform classification in this higher-dimensional space without actually computing the transformation.

### Linear Kernel

The linear kernel is the simplest kernel. It assumes that the data is already linearly separable. The kernel function is:

$$
K(x, y) = x \cdot y
$$

This means it just computes the dot product of the data points.

### Polynomial Kernel

The polynomial kernel allows SVM to separate data that is not linearly separable by applying a polynomial transformation to the data. The formula is:

$$
K(x, y) = (x \cdot y + c)^d
$$

where:

- $c$ is a constant.
- $d$ is the degree of the polynomial.

This kernel can create complex decision boundaries that are not just straight lines or planes.

### Sigmoid Kernel

The sigmoid kernel is inspired by the activation function of a neural network. It can be used for classification tasks that require non-linear decision boundaries. Its formula is:

$$
K(x, y) = \tanh(\alpha x \cdot y + c)
$$

where $\alpha$ and $c$ are constants.

The sigmoid kernel maps the data to a space that may create more complex decision boundaries, though it is less commonly used than other kernels like linear or polynomial.

## SVM Classifier

1. Start with labeled data (training data) where each data point is associated with a class label.
2. Decide on a kernel function depending on the data's nature (linear, polynomial, sigmoid, etc.).
3. The SVM tries to find a hyperplane that maximizes the margin between the two classes, ensuring that the data points are as far from the hyperplane as possible.
4. Use an optimization algorithm to solve the following optimization problem:
    - Maximize the margin.
    - Ensure that each data point is correctly classified (based on its label).
5. The data points that are closest to the hyperplane are called **Support Vectors**. These points define the decision boundary.
6. Once the hyperplane is found, you can use the model to predict the class of new, unseen data by checking which side of the hyperplane the new data point falls on.

### Pros & Cons

| **Classifier** | **Pros** | **Cons** |
| - | - | - |
| SVM | Effective for high-dimensional data. Works well on small datasets | Computationally expensive, especially with large datasets |
