# Neural Networks

## Exercise 1

### Sample Network

...

### Question 1

...

Pattern:

| **$x_1$** | **$x_2$** |
| - | - |
| 0 | 0 |
| 0 | 1 |
| 1 | 0 |
| 1 | 1 |

Weighted sums:

- $s_1 = 4x_1 + 9x_2 - 8$
- $s_2 = 8x_1 - x_2 - 6$
- $s_3 = 7h_1 - 4h_2 + 1$
- $s_4 = 9h_1 - 3h_2 - 6$

Step Activation Function:

| **Nodes** | **Prediction** |
| - | - |
| $x_1 = 0 \to s_1 = -8 \to h_1 = 0 \to s_3 = 1 \to y_1 = 1$<br>$x_2 = 0 \to s_2 = -6 \to h_2 = 0 \to s_4 = -6 \to y_2 = 0$ | $y_1$ |
| $x_1 = 0 \to s_1 = 1 \to h_1 = 1 \to s_3 = 8 \to y_1 = 1$<br>$x_2 = 1 \to s_2 = -7 \to h_2 = 0 \to s_4 = 3 \to y_2 = 1$ | none |
| $x_1 = 1 \to s_1 = -4 \to h_1 = 0 \to s_3 = -3 \to y_1 = 0$<br>$x_2 = 0 \to s_2 = 2 \to h_2 = 1 \to s_4 = -9 \to y_2 = 0$ | none |
| $x_1 = 1 \to s_1 = 5 \to h_1 = 1 \to s_3 = 4 \to y_1 = 1$<br>$x_2 = 1 \to s_2 = 1 \to h_2 = 1 \to s_4 = 0 \to y_2 = 1$ | none |

ReLU Activation Function:

| **Nodes** | **Prediction** |
| - | - |
| $x_1 = 0 \to s_1 = -8 \to h_1 = 0 \to s_3 = 1 \to y_1 = 1$<br>$x_2 = 0 \to s_2 = -6 \to h_2 = 0 \to s_4 = -6 \to y_2 = 0$ | $y_1$ |
| $x_1 = 0 \to s_1 = 1 \to h_1 = 1 \to s_3 = 8 \to y_1 = 8$<br>$x_2 = 1 \to s_2 = -7 \to h_2 = 0 \to s_4 = 3 \to y_2 = 3$ | $y_1$ |
| $x_1 = 1 \to s_1 = -4 \to h_1 = 0 \to s_3 = -7 \to y_1 = 0$<br>$x_2 = 0 \to s_2 = 2 \to h_2 = 2 \to s_4 = -12 \to y_2 = 0$ | none |
| $x_1 = 1 \to s_1 = 5 \to h_1 = 5 \to s_3 = 32 \to y_1 = 32$<br>$x_2 = 1 \to s_2 = 1 \to h_2 = 1 \to s_4 = 36 \to y_2 = 36$ | $y_2$ |
