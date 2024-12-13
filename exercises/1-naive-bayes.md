# Naïve Bayes

## Exercise 1

### Sample Dataset

| HCI | WAT | BUD | PHY | Target |
| - | - | - | - | - |
| no | yes | no | yes | rep |
| no | no | no | yes | rep |
| yes | no | yes | no | dem |
| yes | yes | yes | yes | dem |
| no | no | no | yes | rep |
| no | yes | no | yes | rep |
| no | yes | yes | no | dem |
| no | yes | yes | no | dem |
| no | no | no | no | dem |
| yes | yes | yes | no | dem |
| yes | yes | no | yes | rep |
| yes | yes | no | no | dem |

### Question 1

...

Using the given prior probabilities, we have:

- $\hat{p}(HCI = yes | P = dem) = \frac{4}{7}$
- $\hat{p}(WAT = no | P = dem) = \frac{2}{7}$
- $\hat{p}(BUD = no | P = dem) = \frac{2}{7}$
- $\hat{p}(PHY = yes  | P = dem) = \frac{1}{7}$

And:

- $\hat{p}(HCI = yes | P = rep) = \frac{1}{5}$
- $\hat{p}(WAT = no | P = rep) = \frac{2}{5}$
- $\hat{p}(BUD = no | P = rep) = \frac{5}{5}$
- $\hat{p}(PHY = yes  | P = rep) = \frac{5}{5}$

Using these estimates, we have:

- $\frac{4}{7} \cdot \frac{2}{7} \cdot \frac{2}{7} \cdot \frac{1}{7} = \frac{4}{12^2} = \frac{4}{144}$
- $\frac{1}{5} \cdot \frac{2}{5} \cdot \frac{5}{5} \cdot \frac{5}{5} = \frac{2}{5^2} = \frac{2}{25}$

Since $\frac{4}{144} < \frac{2}{25}$, we estimate that the person is a republican.

### Question 2

...

Using the given prior probabilities, we have:

- $\hat{p}(HCI = no | P = dem) = \frac{3}{7}$
- $\hat{p}(WAT = yes | P = dem) = \frac{5}{7}$
- $\hat{p}(BUD = no | P = dem) = \frac{2}{7}$
- $\hat{p}(PHY = no | P = dem) = \frac{6}{7}$

And:

- $\hat{p}(HCI = no | P = rep) = \frac{4}{5}$
- $\hat{p}(WAT = yes | P = rep) = \frac{3}{5}$
- $\hat{p}(BUD = no | P = rep) = \frac{5}{5}$
- $\hat{p}(PHY = no | P = rep) = \frac{5}{5}$

Using these estimates, we have:

- $\frac{3}{7} \cdot \frac{5}{7} \cdot \frac{2}{7} \cdot \frac{6}{7} = \frac{180}{7^4} = \frac{180}{2401}$
- $\frac{4}{5} \cdot \frac{3}{5} \cdot \frac{5}{5} \cdot \frac{5}{5} = \frac{60}{5^4} = \frac{60}{625}$

Since $\frac{180}{2401} < \frac{60}{625}$, we estimate that the person is a democrat.
