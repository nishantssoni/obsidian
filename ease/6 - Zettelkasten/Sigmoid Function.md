2025-01-25 13:16

Status:

Tags:[[maths]] [[functions]]

# Sigmoid Function


The **sigmoid function** is a mathematical function with an "S"-shaped curve, commonly used in machine learning and statistics.

## Definition
The sigmoid function is defined as:
$$
\sigma(x) = \frac{1}{1 + e^{-x}}
$$

## Properties
- **Range**: $(0, 1)$
- **Domain**: $(-\infty, \infty)$
- **Derivative**: 
$$
\sigma'(x) = \sigma(x) \cdot (1 - \sigma(x))
$$

## Applications
- **Machine Learning**: Used as an activation function in neural networks.
- **Logistic Regression**: Maps predictions to probabilities.
- **Biology**: Models growth curves or responses to stimuli.

### Graph
The sigmoid curve transitions smoothly from 0 to 1 as $x$ increases.


# References