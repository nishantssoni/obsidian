2025-02-17 08:56

Status:

Tags:

# PCA Mathematical objective function

### variance maximization formulation of PCA:
- $u_{1}$ : Unit vector: in the direction where maximum variance of projection of $x_{i}$ exists:
	- $||u_{1}|| = 1$ 
	- $x_{i}^{'} = \ proj \ x_{i} \ in \ u_{1} =  \frac{u_{1}.x_{i}}{||u_{1}||^{2}} = u_{1}^{T}x_{i}$
	- $u_{1}^{T}x_{i}$ from this we can get any point $x_{i}$ in line $u_{1}$ 
	- If $x_{i} = \bar{x}$ (mean) then $u_{1}^{T}x_{i}$ is a mean vector in line $u_{1}$.
	- ![[Pasted image 20250217090528.png]]
- Task:
	- find u1 , such that the variance of projection of xi in u1 is maximum.(because we want an unit vector(direction) u1 such that the maximum point(variance) lies in that direction).
- $var(u_{1}^{T}x_{i})_{i=1}^{n} = \frac{1}{n} * \sum^{i=1}_{n}(u_{1}^{T}x_{i} - u_{1}^{T}\bar{x})^{2}$ where $\bar{x}$ becomes zero.
- Then variance is:
	- $var(u_{1}^{T}x_{i})_{i=1}^{n} = \frac{1}{n} * \sum^{i=1}_{n}(u_{1}^{T}x_{i})^{2}$
- We want $u_{1}$ such that the above equation(variance) is maximum.


This is optimization problem:
- Objective
	- $max(\frac{1}{n} * \sum^{i=1}_{n}(u_{1}^{T}x_{i})^{2})$
- Constraint:
	- $u_{1}^{T}u_{1} = 1 = ||u_{1}||^{2}$
	- $u_{1}$ is always a unit vector.


# References
[[Objective Function]]
[[Logistic Regression Mathematic Formulation of Objective Function]]