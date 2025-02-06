2025-02-03 12:34

Status:

Tags: [[regression]]

# Linear Regression Geometric intuition of Linear Regression

Logistic Regression:
- A two class classification technique.

Linear Regression:
- it is a actual regression technique.
- Find a hyper plane that best fits the training data(continuous variable data)
- given a dataset $D = <x_{i},y_{i}>^{n}_{i=1} where, \ x_{i} \epsilon R^{n}, \ y_{i} \epsilon R$
- here $y_{i}$ belong to real number where in logistic regression it belong to one or two classes.

$$
y_{i} = W^{T}x_{i} + b
$$
where it is equation of the plane with b is intercept term

![[Pasted image 20250203123442.png]]
- we have to choose π such that it best fit the data.
- The points that are not on the hyper plane have errors due to incorrect prediction. e.g: $x_{1}$ doesn't get $y_{1}$ as prediction

$$
error = true \ value - predicted  \ value
$$

### Task:
- Minimize the sum of errors across the training data.
# References