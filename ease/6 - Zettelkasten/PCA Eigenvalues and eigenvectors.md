2025-02-18 09:29

Status:

Tags:

# PCA Eigenvalues and eigenvectors

- Let we have a Covariance matrix S , and we know the Covariance matrix is column standardized which means each column mean is 0, and variance of each column is 1.
- And also S is a square symmetric matrix of (d * d) dimensions( see covariance matrix for reference).

##### Solution to the optimization problems:
- Eigenvalue of S: λ1 , λ2 , λ3 , λ4 , …. (λ1 > λ2 > λ3 > λ4 …. )
- Eigenvectors of S: V1, V2 , V3, V4 , …
- λ1 corresponds to V1 , λ2 corresponds to V2 and so on.
- Def: If $\lambda_{1} V_{1} = S_{d \ x \ d} V_{1}$ , satisfy then λ1 and V1 are Eigenvalue and Eigenvector.
- **λ1 is a scalar** which is the Eigenvalue of S and V1 of dimensions (d * 1) is the Eigenvector corresponding to λ1.
- If S is (d* d) dimension then there are d numbers of pairs of eigenvalues and eigenvectors.
- **Eigen vectors are perpendicular to each other.** This implies that the dot product of pairs of Eigen vectors is zero. $V_{i}^{T}V_{j} = 0$
- **Now our u1 = V1 = Eigenvector of S (= $X^{T}X$) corresponding to largest Eigenvalues (= λ1 )**. ( we can prove this later)


- Steps to find:
	- X: Column Standardized
	- $S = X^{T}X * \frac{1}{n}$ ( covariance matrix)
	- Compute the values of eigenvalue and eigenvector. λ1 , V1 = eigen(s).
	- u1 = V1 direction with maximum variance.

#### Geometric interpretations:
- $\frac{\lambda_{1}}{\sum(\lambda_{i})} =$ % of variance preserved on u1 , V1 max variance, V2 second max var, V3 third max var, …
- Eigen Vectors provide direction of maximum variance(u1).
- Eigen values provide a percentage of variance preserved with each Eigenvector.

![[Pasted image 20250218094229.png]]
- IP = information preserved
- In the first diagram we get all points in V1, and V2 has no spread so if we reduce it to one dimension then we lose 0% of information. (IP = 100%)
- In the second diagram we get ¾ points in V1 and V2 has ¼ points so if we reduced it to one dimension then we lose 25% of information.(IP = 100%)
- In the third diagram we get ⅗ points in V1 and V2 has ⅖ points so if we reduce it to one dimension then we lose 40% of information.(IP = 100%)
- In the second diagram we get ½ points in V1 and V2 has ½ points so if we reduced it to one dimension then we lose 50% of information.(IP = 100%)
# References
[[Dimensionality reduction Co-variance of a Data Matrix]]
[[Probability and Statistics Co-variance]]