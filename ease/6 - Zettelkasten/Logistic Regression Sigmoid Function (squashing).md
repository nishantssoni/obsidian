2025-01-24 23:42

Status:

Tags:[[regression]] [[functions]]

# Logistic Regression Sigmoid Function (squashing)



The expression $y_i * W^T x_i$ represents the signed distance. If it is positive, the class is correctly classified; if it is negative, the class is incorrectly classified.

## Objective:
Find the best $W$ that maximizes the sum of signed distances.

---

### CASE 1
![[image.NE7V02.png]]

Now,  
$$ \sum_{i=0}^n y_i * W^T x_i = 1 + 1 + \dots + (-100) = -90 $$  
In this case, there are 10 correctly classified points and one incorrectly classified point, which is an outlier. This outlier impacts the entire decision, meaning that outliers can significantly affect the $W$ values.

---

### CASE 2
![[image.SKHB12.png]]

Now,  
$$ \sum_{i=0}^n y_i * W^T x_i = (1 + 2 + \dots) + (-1 - 2 - \dots) + 1 = +1 $$  
We choose Case 2 because $1 > -90$, but upon deeper consideration, Case 2 provides better accuracy. It classifies 10 points correctly, and despite the outlier, it is preferred.

We observe that the formulation is highly sensitive to outliers or changes in the training data. Therefore, we will use **squashing** to mitigate this impact.

---

## Idea of Squashing:

- If the signed distance is small, we use it as is.
- If the signed distance is large, we make it smaller.

The **sigmoid function** has this property.

---

### Tapering:

![[image.DSZW02.png]]

In the context of a sigmoid function, **tapering** generally refers to techniques that modify the shape of the sigmoid curve to improve its behavior in certain scenarios.

Here, we have $t = y_i * W^T x_i$.

- The range of the sigmoid function is [0, 1].
- The distances are squashed from $[-\infty, +\infty]$ to [0, 1].

The sigmoid function is differentiable and has a probabilistic interpretation, which helps in solving the optimization problem. For example:
- If a point lies on the hyperplane ($W^T x = 0$), the probability of the point belonging to the positive or negative class is 0.5. This can be seen from $\text{sigmoid}(0) = 0.5$.

---

### Key Takeaways:

- Maximizing the sum of signed distances is prone to outliers.
- We aim to maximize the sum of the sigmoid of signed distances, which is **outlier-resistant**.
	- ![[image.7XM202.png]]
- The sigmoid function is differentiable, which is essential for solving optimization problems.





# References