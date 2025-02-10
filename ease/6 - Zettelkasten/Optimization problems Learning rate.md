2025-02-10 09:36

Status:

Tags: [[maths]]

# Optimization problems Learning rate

**Gradient Descent Update equation:**
$$
x_{i} = x_{i-1} - r*\left[ \frac{df}{dx} \right]_{x_{i-1}}
$$
where $r$ is learning rate.


- If the learning rate is too high, gradient descent takes large steps when trying to find the optimal point. Instead of getting closer to the minimum, it jumps back and forth across it. This back-and-forth movement is called oscillation, and it prevents the algorithm from settling at the best solution.

- To solve this, we reduce the learning rate over time. By taking smaller and smaller steps with each iteration, the algorithm slows down as it approaches the minimum. This helps it avoid jumping over the optimum and ensures it eventually converges to the best solution.

# References
[[Optimization problems Gradient descent geometric intuition]]