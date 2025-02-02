2025-01-31 16:35

Status:

Tags:[[regression]]

# Logistic Regression Train & Run time space and time complexity

**Training Logistic Regression:**
	Solving the optimization problem using Stochastic Gradient Descent.

> [!info] 
>  Train time:
> - Time complexity: O(nd)
> 
Run time:
> - Space: O(d)
> - Time: O(d)

**IF d is small**:
- Logistic Regression is very good for low latency applications.
- popular algorithm for internet companies, memory efficient at run time.

**If dimensionality is large:**
- Apply L1 regularization with reasonable value of $\lambda$  which induce Sparsity which reduce run time complexity. it make less important features weights = 0.
- As the hyper parameter $\lambda$ increases Sparsity also increases.
- this achieves both a suitable bias variance trade off and the low latency requirements.

- As λ increases, bias increases, latency decreases and Sparsity increases so its a ==bias vs variance vs Latency== trade off in real world.
- But the model is just a working model not an optimized model as regularization and Sparsity are induced.

> [!note] 
>  **Sometimes having working model is more important then having a optimized model which doesn't fit requirement.**
> - e.g if you want latency as first priority then you can trade off little bias etc, it not the best model but it delivers in the given timeframe.


# References
[[Logistic Regression L1 regularization and sparsity]]
