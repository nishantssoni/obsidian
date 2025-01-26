2025-01-26 14:11

Status:

Tags: [[regression]]

# Logistic Regression L2 Regularization Overfitting and Underfitting

The optimization problem we have :
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i}) \right) \ where \ y_{i} = [-1, 1]
$$

$$Let \ Z_{i} = y_{i} W^{T}x_{i}$$
$$W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-Z_{i}) \right)$$

Now if we plot $\exp(-Z_{i})$ then it is always $\exp(-Z_{i})\geq0$
then we can say that,
![[Pasted image 20250126145314.png]]

$$
1 + \exp(-Z_{i}) \geq 1
$$

then,
$$
\log(1 + \exp(-Z_{i})) \geq 0
$$

so,
$$
argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-Z_{i}) \right) \geq 0
$$


==so the least value of the equation is 0==


- If $Z_{i} \to \infty$   then the $\left( \sum_{i=1}^{n} \log(1+\exp(-Z_{i}) \right) = 0$ becaue $\log(1) = 0$
- ==we have $y_{i}W^{T}x_{i}$ here W is only we can change so we find optimum W so the whole value become positive and if the value is positive that means the value is correctly classified.
- If the selected W results in correctly classifying all training points and if $Z_{i} \to \infty$, then W is the best W on training data.
- But, this is a case of overfitting on training data as this does not guarantee good performance on test data.
- Or, here is also case that $W_{i}$ is becoming $-\infty \ or +\infty$ then we get least value for $W^{*}$
- the train data may contain outliers to which the model has been perfectly fitted.
- The overfitting tendency is constrained by using regularization.
W*
= argmin summ log((1+ exp(-yi WT xi)) + λWTW
= argmin summ log((1+ exp(-yi WT xi)) + λ*||W||2
The regularization term will constrain W from reaching +infinity or - infinity;


λ is a hyper parameter of regularization; this is determined using cross
validation;
If λ = 0 there is not regularization; the loss term optimization results in an
overfitting model  high variance;
If λ is large then the loss term is diminished; the training data does not
participate in the optimization and we are just optimizing for the regularization
term; this leads to an underfitting model  high bias;

# References