2025-02-09 06:29

Status:

Tags: [[maths]]

# Optimization problems Gradient descent geometric intuition

- Gradient descent is a Iterative algorithm.
- Initially we make a guess on the solution and we move towards the solution iteratively through solution correction.
- Slope reaches zero when arriving at the optimum.

steps of Gradient Descent:
1. Pick an initial point = $x_{old}$ randomly
2. $x_{new} = x_{old} - r*\left[ \frac{df}{dx} \right]_{x_{old}}$ where r = step size, ==r is always +ve==.
3. update and iterate step 2 until  difference between two consecutive x is very small then we can say that it is optimum solution.

```
In addition the gradient decreases at each iteration, because slope also reduces at each iteration.

first iteration update will be large, then successive updates decreases until optimum is reached.

```
# References