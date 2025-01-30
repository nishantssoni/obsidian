2025-01-29 15:44

Status:

Tags:[[regression]] [[ml_loss]]

# Logistic Regression Loss minimization interpretation

let the idea optimization model be:
- +1 for incorrectly classified
- 0 for correctly classified
- so the $W* = argmin (number \ of \ incorrctly \ classified \ points)$
- For optimization the function should be differentiable.
- zero one loss function is discontinous at x = 0 which implies not diffrentiable so we use good approxiamation like logistic loss etc.
- ![[loss_functions.png]]
					`the above image is Zi vs Loss` 

- Logistic loss is a good approximation of 0-1 loss (step loss).

> [!note] 
>  - with logistic loss we get Logistic regression.
>  - With hinge loss we will have Support Vector Machines
>  - With exponent loss we get AdaBoost
>  - With Squared Loss we get linear regression
>  

# References