2025-02-02 12:45

Status:

Tags:[[regression]]

# Logistic Regression How does imbalance data impact LR geometrically

**Let there are 20 +ve and 3 -ve points(Imbalance data)**
- we want to maximize the following:
![[Drawing 2025-01-29 16.42.01.excalidraw 2.svg]]
$$
argmax \sum_{i=1}^{n} \sigma(y_{i}w^{T}x_{i}), where \ \sigma = sigmoid
$$
now,
$$
\pi_{1} = (20 * 0.8) + ( 3 *0.8) = 18.4
$$
now, 
$$
\pi_{2} = (20 * 1) + (3 * 0) = 20
$$
- because sigmoid of large +ve value is 1 and large -ve value is 0, thats why we take 1 and 0.
- **so in this case Logistic regression choose $\pi_{2}$ as hyperplane it choose further hyperplane because it want to classify as much as point to be positive.**


**Let there are 20 +ve and 20 -ve points(balance data).
![[Drawing 2025-01-29 16.42.01.excalidraw 1.svg]]

we want to maximize the following:
$$
argmax \sum_{i=1}^{n} \sigma(y_{i}w^{T}x_{i}), where \ \sigma = sigmoid
$$
now,
$$
\pi_{1} = (20 * 0.8) + ( 20 *0.8) = 32
$$
now, 
$$
\pi_{2} = (20 * 1) + (20 * 0) = 20
$$

- **so in this case Logistic regression choose $\pi_{1}$ as hyperplane.
# References
[[Logistic Regression Sigmoid Function (squashing)]]
[[Logistic Regression Mathematic Formulation of Objective Function]]