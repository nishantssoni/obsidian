2025-02-10 09:35

Status:

Tags: [[maths]]

# Optimization problems Gradient descent for linear regression

**The equation for linear regression without relgularization is**:
$$
W^{*} = argmin_{w}\left( \sum ^{n}_{i=1}(y_{i} - W^{T}x_{i})^{2} \right)
$$
here $y_{i} \ and \ x_{i}$ are constants which comes from training data. so the function is in W so the equation is :
$$
L(W) = argmin_{w}\left( \sum ^{n}_{i=1}(y_{i} - W^{T}x_{i})^{2} \right)
$$
and we have to make 
$$
\delta_{w}L = \left( \sum ^{n}_{i=1}2(y_{i} - W^{T}x_{i})(-x_{i}) \right)
$$

now for gradient descent steps are:
1. pick a random vector $W_{0}$ of d dimensions
2. $W_{1} = W_{0} - r * \sum ^{n}_{i=1}2(y_{i} - W_{0}^{T}x_{i})(-x_{i})$
3. repeat step 2 and get $W_{0},W_{1},\dots,W_{k},W_{k+1}$
4. when $W_{k+1} \ll W_{k}$ then we select $W_{*}$ as $W_{k}$

==With Gradient descent we need to compute the updates over all data points which is expensive==

> [!info] 
> so mathematician use a beautiful hack called stochastic gradient descent for computing which is by far less computing intensive than GD. 


# References
[[Linear Regression Mathematical formulation]]
[[SGD algorithm Intro]]