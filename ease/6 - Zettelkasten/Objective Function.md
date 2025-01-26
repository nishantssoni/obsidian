2025-01-25 13:53

Status:

Tags:[[maths]] [[functions]]

# Objective Function


The **objective function** is a mathematical expression that defines the goal of an optimization problem. It is the function we aim to minimize or maximize.

## Definition
Given a function $f(x)$, the objective is to find:
- $\min f(x)$ (minimization) or
- $\max f(x)$ (maximization),

where $x$ is the decision variable(s) within a feasible domain.

## Examples
1. **Mathematics**:
   - Minimize $f(x) = x^2 + 4x + 5$
   - Maximize $f(x) = -x^2 + 3x$

2. **Machine Learning**:
   - Regression: Minimize the **mean squared error (MSE)**:
     $$
     \text{MSE} = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2
     $$
   - Classification: Minimize the **cross-entropy loss**:
     $$
     \text{Loss} = -\frac{1}{n} \sum_{i=1}^n \left[ y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) \right]
     $$

3. **Optimization**:
   - Linear programming: Maximize $f(x) = c^T x$ subject to $Ax \leq b$.
   - Nonlinear optimization: Minimize $f(x) = x_1^2 + x_2^2$ subject to constraints.

## Key Points
- **Objective function** is the core of optimization problems.
- It can involve multiple variables, constraints, or complex relationships.
- In machine learning, it is often referred to as the **loss function**.


# References