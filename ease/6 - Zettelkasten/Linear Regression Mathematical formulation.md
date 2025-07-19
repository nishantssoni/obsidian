2025-02-03 12:57

Status: #hard 

Tags: [[regression]]

# Linear Regression Mathematical formulation

objective:
- find best fit line which minimize sum of errors

![[Pasted image 20250203125837.png]]
**As there are positive and negative valued errors we need to make the values free from signs, we can use squared error**

Formulation:
$$
(W^{*}, W_{0}) = argmin\left( \sum_{i=1}^{n} (y_{i} - \hat{y}_{i})^{2} \right)
$$
Where $W^{*}$ is vector and $W_{0}$ is scalar.
$$
\hat{y}_{i} = f(x) = W^{T}x_{i} + x_{0}
$$
so the equation became and it is also our optimization problem
$$
(W^{*}, W_{0}) = argmin\left( \sum_{i=1}^{n} (y_{i} - (W^{T}x_{i} + x_{0}))^{2} \right)
$$

**The term inside argmin is called square loss and we want to minimize the square loss.**

> [!info] 
> Linear regression is also refered as odinary least squares(OLS) or Linear least squares.


Regularization:
$$
(W^{*}, W_{0}) = argmin\left( \sum_{i=1}^{n} (y_{i} - (W^{T}x_{i} + x_{0}))^{2} + \lambda||W||_{2}^{2} \right)
$$
- We can also use L1 regularization.
- L1 regularization creates sparsity just like logistic regression.


> [!important] 
> just like logistic regression all three formula geometry, probablity and loss minimization are similar.


**Loss minimization:**
- For classification task:
	- $Z_{i} = y_{i}f(x_{i})$ where $Z_{i} = W^{T}x_{i}$ for logistic regression we have sigmoid function.
	- we can also have step function or hinge loss which form other ML algorithms.
	- if the value is positive it classified the point and for -ve it failed.
- For regression task:
	- $Z_{i} = y_{i} - f(x_{i})$ where, $f(x_{i}) = W^{T}x_{i} + W_{o}$ and the loss function is squared loss.
	- for regression we don't have the concept of +ve or -ve.
	- we squared the loss function so we get -ve or +ve error our loss is always +ve.
	- the loss function forms a parabola.

Terminology:
1. Linear regression with L2 regularization is also referred to as "Ridge Regression"
2. Linear regression with L1 regularization is also referred to as "Lasso Regression".
3. Linear regression with l1+L2 regularization is also referred to as "Elastic Net Regression".

**Why use Regularization in Linear Regression:**
- For logistic regression we introduced regularization to constrain weight elements reaching infinity.
- In real world we round up the values to an easily understandable decimal, this results in small errors even though we know the underlying relationships. e.g we write 176 cm but ther original is 176.4 cm, so that why we introduce little noise to the original data

Let assume:
- function from where data created : $Y_{i} = 2x_{i_{1}} + 3x_{i_{2}} + 0x_{i_{3}}$ so the weights are <2,3,0> respectively.
- we generated 10k points from the function now if we give only the dataset you can get the weights by linear regression.
- But in the real world we can't get exact data the data may be round off so for matching like simulated data we add little noise to the data $\epsilon_{o}$.


**Case 1: Logistic Regression Without Regularization**

- Without regularization, noise in the data can propagate to the weight values because the model only optimizes the squared loss.
- As a result, the learned weights may capture noise, leading to values like **<2.1, 3.06, 0.12>**, which are influenced by irrelevant variations in the data.

**Case 2: Logistic Regression With Regularization**

- To reduce the impact of noise on the weight vector, regularization is introduced.
- Without regularization, the only way to influence the weights is through minimizing the squared loss. However, with regularization, the model also controls the magnitude of the weights.
- The regularization term encourages smaller weights, helping to prevent overfitting, while the squared loss focuses on reducing prediction error.
- Regularization effectively pulls the weights towards zero(but the weight cant be zero because of squared loss), limiting the model's sensitivity to noise in the data.
- As a result, the learned weights are closer to the true values, such as **<2.01, 3.003, 0.002>**, reflecting reduced overfitting and improved generalization.



# References
[[Logistic Regression Geometric Intuition]]
[[Logistic Regression L1 regularization and sparsity]]