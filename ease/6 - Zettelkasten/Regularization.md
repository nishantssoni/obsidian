2025-01-27 10:10

Status:

Tags: [[maths]]

# Regularization

**Regularization** is a technique in machine learning and optimization used to prevent overfitting by adding a penalty term to the objective (or loss) function. It encourages simpler models by discouraging extreme parameter values.

## General Form
For a loss function $L(\theta)$, regularization modifies it by adding a penalty term $R(\theta)$:
$$
L_{\text{regularized}}(\theta) = L(\theta) + \lambda R(\theta)
$$
- $R(\theta)$: Regularization term
- $\lambda$: Regularization strength (hyperparameter)

## Types of Regularization

1. **L1 Regularization (Lasso)**:
   Adds the absolute values of the parameters:
   $$
   R(\theta) = \|\theta\|_1 = \sum_i |\theta_i|
   $$
   - Encourages sparsity (some weights become zero).
   - Used for feature selection.

2. **L2 Regularization (Ridge)**:
   Adds the squared values of the parameters:
   $$
   R(\theta) = \|\theta\|_2^2 = \sum_i \theta_i^2
   $$
   - Prevents large weights but keeps all parameters small.
   - Common in regression and neural networks.

3. **Elastic Net**:
   Combines L1 and L2 regularization:
   $$
   R(\theta) = \alpha \|\theta\|_1 + (1 - \alpha) \|\theta\|_2^2
   $$
   - Balances sparsity and smoothness.

## Applications
1. **Machine Learning**:
   - Prevents overfitting by penalizing complex models.
   - Common in linear regression, logistic regression, and deep learning.

2. **Optimization**:
   - Ensures stability of solutions by penalizing large parameters.

3. **Neural Networks**:
   - Regularization techniques like weight decay (L2), dropout, and batch normalization reduce overfitting.

## Key Points
- **Trade-off**: Higher $\lambda$ increases regularization but may underfit.
- Regularization improves generalization on unseen data.


# References