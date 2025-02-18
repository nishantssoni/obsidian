2025-02-18 09:23

Status:

Tags:

# PCA Alternative formulation of PCA distance minimization

### Distance Normalization formulation of PCA:
![[Pasted image 20250218092405.png]]

#### Task
- find u1 such that distances of the data points to u1 is minimum.
- u1 is unit vector.

#### Objective
- Projection of $x_{i}$ in $u_{1}$ : $u_{1}^{T}x_{i}$
- $d_{i}= ||x_{i}|| = x_{i}^{T}x_{i}$
- $min\left( \sum_{i=1}^{n} ((x_{i}^{T}x_{i}) - (u_{1}^{T}x_{i})^{2}) \right)$
#### Constraint:
- $u_{1}^{T}u_{1} = 1 = ||u_{1}||^{2}$
- **With some simple transformation in optimization we can prove that the u1 which achieves minimization(in distance minimization) is the same as the u1 which maximizes(variance maximization)** . We can prove this later.

# References