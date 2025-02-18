2025-02-14 09:29

Status:

Tags:

# SGD algorithm Constrained optimization & PCA

==The problem with constraint is called Constrained optimization problem==

The general constrained optimization problem:
- $x^{*}=max_{x} f(x)$ : objective function
- such that $g(x) = c$ : equality constraint
- $h(x) \geq d$  : inequality constraint


For Finding optimum under constraints: We need to modify the objective function using Lagrangian Multipliers

$$
L_{x,\lambda,\mu} = f(x) - \lambda(g(x) - c) - \mu(d - h(x))
$$
here,
- here L is called lagrangian
- $\lambda,\mu$ are called lagrangian multipliers, where both are $\lambda \geq_{0},\mu\geq 0$

now we take derivative of all and set it to 0
$$
\frac{\delta L}{\delta x} = 0; \frac{\delta L}{\delta \lambda} = 0; \frac{\delta L}{\delta \mu} = 0;
$$
by solving the equation let say we got $\tilde{x}$ this is equal to the $x^{*}$
$$
\tilde{x} = x^{*} = max_{x} f(x)
$$

**The optimization problem in PCA :**
- Objective
	- $max(\frac{1}{n} * \sum^{i=1}_{n}(u_{1}^{T}x_{i})^{2})$
- Constraint:
	- $u_{1}^{T}u_{1} = 1 = ||u_{1}||^{2}$
	- $u_{1}$ is always a unit vector.

PCA can be reformulated as:
![[Pasted image 20250218124910.png]]
**Su = λu, then λ = Eigen value and u is the Eigen vector of S**

# References
[[PCA Geometric intuition]]
[[PCA Mathematical objective function]]
[[PCA Eigenvalues and eigenvectors]]