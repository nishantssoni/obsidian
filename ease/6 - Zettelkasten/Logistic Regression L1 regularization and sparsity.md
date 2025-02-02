2025-01-29 06:39

Status:

Tags: [[regression]] 

# Logistic Regression L1 regularization and sparsity

The optimization problem we have :
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i}) \right) \ where \ y_{i} = [-1, 1]
$$

If we put L1 regullarizer here:
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i})  + \lambda ||W||_{1} \right)
$$
- it is absolute value of W so it also acts like L2 norm which prevent the whole equation $\to \pm \infty$
- L1 regularization often used in Logistic Regression when we want sparsity, It induces Sparsity in the W vector.
- Solution to Logistic Regression is said to be sparse if many $W_{i}$ 's are Zero.

> [!note] 
> - Less important features become vanished in Logistic Regression with L1 Regularization.
> - If L2 Regularization is used Weight for less important features becomes small but remains non-zero.

> [!info] 
> Elastic net: Combines L1 and L2 regularization
> - $W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i})  + \lambda_{1} ||W||_{1} +\lambda_{2} ||W||^{2}_{2} \right)$
> - now it has two hyperparameter $\lambda_{1} , \lambda_{2}$
>  



# References
[[Regularization]]
[[Sparsity]]
[[Logistic Regression L2 Regularization Overfitting and Underfitting]]
