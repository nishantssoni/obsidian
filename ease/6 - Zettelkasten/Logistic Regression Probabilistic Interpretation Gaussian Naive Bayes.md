2025-01-29 07:30

Status:

Tags:[[regression]]

# Logistic Regression Probabilistic Interpretation Gaussian Naive Bayes

> [!info] 
> claim by applied ai:
> - No book encountered that covers all of geometric, probabilistic and loss minimization interpretations of logistic regression.

> [!important] 
> In Naive Bayes:
> 1. real valued features are Gaussian distributed.
> 2. class label is a Bernoulli random variable $Y_{i} =$ 1 or 0.

==**In a Nutshell LR = Gaussian Naive bayse($P(X_{i}|Y_{i})$) + Bernoulli($Y_{i}$)==**
### Assumption:
- if $X_{i}$ is a feature, $P(X_{i} | Y_{i})$  is a Gaussian distribution( it is normally distributed ) and $X_{i}$‘s are conditionally independent.


**Geometri interpretation**
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i})  + regularization \ term \right), where \ y_{i} = \pm 1
$$
**Probablistic Interpretation**
$$
W^{*} = argmin \sum_{i=1}^{n} (-y_{i} \log(p_{i}) - (1-y_{i})\log(1-p_{i}) + regularization \ term)) \ where \ p_{i} = \sigma(w^{T}x_{i}) \ a nd \ y_{i} = 0,1
$$
here $\sigma = simoid \ function$

### comparing both proablity and geometry equation

Case 1 (if $y_{i} = +ve$):
- geometry($y_{i} = +1$)
	- $\log(1+\exp(-W^{T}x_{i})$
- probablity($y_{i} = +1$)
	- $-1*\log\left( \frac{1}{1-p_{i}} \right) \implies \log(1+\exp(-W^{T}x_{i}))$
Case 2 (if $y_{i} = -ve$):
- geometry($y_{i} = -1$)
	- $\log(1+\exp(W^{T}x_{i})$
- probablity($y_{i} = 0$)
	- $-1*\log\left( 1-\frac{1}{1-p_{i}} \right) \implies \log(1+\exp(W^{T}x_{i}))$

==**So From above we can conclude that both form are exactly same**==

#### Links
you can read section 3.1 here for further read, <a href="https://www.cs.cmu.edu/~tom/mlbook/NBayesLogReg.pdf">Tom M. Mitchell book</a>

# References
[[Naive Bayes]]