2025-02-18 09:44

Status:

Tags:

# PCA PCA for dimensionality reduction and visualization

- If we have (d x d) dimensions matrix then we can reduce it to d’ by using PCA. where d >= d’.
- For X:
	- Let us have S of 2 -dimensions( f1 and f2 ). We want to convert it to 1-dimensions then we can get V1 and V2 using the eigen(s) function.
- Transform $X_{i}=[f_{1i},f_{2i}]$ to $x_{i}^{'} = [f_{1i}^{T}V_{1},f_{1i}^{T}V_{2}, ]$ where xi is the value of matrix X and $f_{1i}^{T}V_{1}=i^{th}$ value of f1,column projected to vector V1.
- we can drop xiT V2 as there is not much variance, 2D data point is transformed to 1D.
- If we want to preserve say k% of variance:
- Find d’ such that $\frac{\lambda_{1} + \lambda_{2} + \dots + \lambda_{d}}{\sum ^{d}_{i=1}(\lambda_{i})}=k$%  where d is dimensionality of the input data point. For example d= 100 and it reduces to d’= 51 which can preserve 95% of information.

# References