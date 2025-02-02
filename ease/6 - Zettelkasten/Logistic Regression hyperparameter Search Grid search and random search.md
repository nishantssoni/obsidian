2025-01-29 16:28

Status:

Tags:

# Logistic Regression hyperparameter Search Grid search and random search

**We have to find $\lambda$  in Logistic regression**
- $\lambda$ is just like:
	- K in kNN is an integer
	- $\alpha$ in Laplace smooting
- K in KNN is integer but Logistic Regression λ is a real valued hyper parameter.
- So, Hyper parameter tuning technique:
	- Grid Seach (Brute force)
		- For λ in `[0.001, 0.01, 0.1, 1, 10, 100]`
		- Compute cross validation error and select the best hyper parameter value from the plot.
		- ![[Drawing 2025-01-29 16.42.01.excalidraw.svg]]
		- people generally take  $\lambda \to [10^{-4},10^{-3},\dots,10^{3},10^{4}]$

**Elastic Net: $\lambda_{1}||W||_{1} + \lambda_{2}||W||_{2}^{2}$**
- we check every thing on the grid and if we find the optimum value we take the current value of $\lambda_{1}, \lambda_{2}$
![[image.2CPW02.png]]
- but for two hyper parameter Multiple computations or training is required.
- As number of hyper parameters increase, the number of training instances increase exponentially.

==**so for avoiding the large computation if hyperparameter is more  we use random search**==

Random Search: 
- we take a smaller set like $\lambda \in [10^{-4},10^{4}]$
- Then we avoids brute force and reduces the time spent for hyper parameter tuning by looking at a smaller set of hyper parameter choices.
- This technique selects random hyperparameter values to compute cross-validation error, ultimately identifying the ==best hyperparameter choices that optimize the algorithm== as good as grid search for large number of hyper parameter.

#### Link
- https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html
- https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html

# References
[[Logistic Regression L2 Regularization Overfitting and Underfitting]]
[[Naive Bayes Laplace or Additive Smoothing]]
[[Grid Search]]