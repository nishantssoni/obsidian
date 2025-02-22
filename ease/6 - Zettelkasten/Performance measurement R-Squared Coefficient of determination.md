2025-02-22 07:55

Status:

Tags:

---

- It is used for a regression model.
- A simple mean model is a model which returns the avg value(or mean) of the whole $y_{i}$
- Sum of squared errors ( $SS_{tot}$)
	- $\sum_{i}^{n}(y_{i} - \bar{y})^{2}$
	- Here we assume $\bar{y}= \hat{y}$
	- $\bar{y}$ is the avg of $y_{i}$ in data (or mean)
	- So it is a sum of square error using a simple mean model.
- Sum of squares of residues($SS_{res}$)
	- $\sum_{i}^{n}(y_{i} - \hat{y})^{2}$
	- $\hat{y}$ is actual predicted value
	- So it is a sum of square of actual minus predicted value
- $R^{2} = 1 - \frac{SS_{res}}{SS_{tot}}$
	- $SS_{res}$ = ss residues
	- $SS_{tot}$= sum of squared error
	- Case 1:
		- $SS_{res} = 0$
		- $R^{2} = 1$
		- Best Value
	- Case 2:
		- $SS_{res} < 0$
		- $0 \leq R^{2} \leq 1$
	- Case 3:
		- $SS_{res} = SS_{tot}$
		- $R^{2} = 0$
		- this model is same as simple mean model
	- Case 4:
		- $SS_{res} \geq SS_{tot}$
		- $R^{2} < 0$
		- This model is worse than a simple mean model


- In an experimental study, the explanatory variable is the variable that is manipulated by the researcher. Explanatory Variable. Also known as the independent or predictor variable, it explains variations in the response variable; in an experimental study, it is manipulated by the researcher.
- The problem with R2 is its value gets increased even if unimportant features are present in the model. Due to this, even the random models also can have higher R2 scores. So we have to adjust R2 which is also called adjusted R-squared.
- $SS_{tot}$ tells you how much variation there is in the dependent variable.
- [Article](https://medium.com/@premvardhankumar/a-deep-understanding-of-logistic-regression-with-geometric-probabilistic-and-loss-minimization-2ced042bdcc7)

![[Pasted image 20250220214601.png]]

==One of the best metric to use to calculate regression model is MSE or adjust R2==



# References