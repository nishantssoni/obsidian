2025-01-29 17:32

Status:

Tags:[[regression]]

# Logistic Regression Feature importance and model interpretability

- ==we know Logistic regression is gaussian naive bayes + Bernoulli ==
- We have d features and through optimization we determine W vector of d dimensionality, each element in W vector corresponds to respective features.
- if we assume: ==that all features are independent==:
	- Then Weight element($W_{j}$'s) values indicate how important the feature is.
- In kNN: we have forward feature selection;
	- Forward feature selection is algorithm independent can be applied for NB and LR
- In NB: Probability values give feature importance (Conditional probabilities)

> [!note] 
>  - In Logistic Regression, Weights can be used to determine feature importance, If absolute value of weight is large then contribution of the corresponding feature is large, thus this feature is important.
>  - And by using most important features model interpretability also increases.
>  - Imagine you have 100 features you can select top 5 features by using absolute value of weights.

> [!example] 
>  let (-1) is female and (+1) is male
>  - so the feature hair length `hl` increases then $P(Y_{q}=-1)$ increases.
>  - so, we can conclude that absolute weight of hair length which is  $|W_{hl}|$ has large -ve value.


# References
[[Logistic Regression Probabilistic Interpretation Gaussian Naive Bayes]]
[[Naive Bayes Handling Numerical features (Gaussian NB)]]
[[model interpretability]]