2025-02-18 11:09

Status:

Tags:

# PCA PCA for dimensionality reduction (not visualization)

==It is using MNIST dataset==

- d >= d’, d’ is the dimension which we want to reduce to.
- If d' = 2 or 3, it is for visualization, but if d’= 200 or any other value , then we are doing data reduction for non-visualization tasks(or making models).
- Stack Eigen vectors horizontally to get Eigen matrix V. Multiply X(standardize matrix) with V to get X’ which is dimensionally reduced.
- d' can be determined by checking explained variance .

The task is to maximize variance:
- Explained variance = % of variance retained = $\frac{\lambda_{1} + \lambda_{2} \dots + \lambda_{n}}{\sum ^{784}_{i=1} \lambda_{i}} * 100$
- n is the number of eigen values which is added to get desired explained variance or the variance you want to get.
- Example:
	- You want to get 90% of variance then put in the formula
	- Then you can get the value of n
	- Now our d’ = n (number of dimensions)
	- Then d’of eigenvectors you want, to get 90% of variance.
# References
[[PCA Visualize MNIST dataset]]