2025-02-02 14:16

Status:

Tags: [[regression]]

# Logistic Regression Non-linearly separable data & feature engineering

**We need to transform features to make it linearly separable**

![[Pasted image 20250202142627.png]]
In the above picture a circularly separable data set can be transformed into linearly separable data set by transforming features into a quadratic space.
- in left side there is feature space with $f_{1} \ and \ f_{2}$ with circular dataset.
- we then feature transform or say feature engineer and make $x_{i_{1}} = x_{i_{1}}^{2} \ and \ x_{i_{2}} = x_{i_{2}}^{2}$
- Now we can separate data using linear hyperplane $\pi^{'}$

**XOR dataset:**

![[Pasted image 20250202172349.png]]

- this type of dataset is called XOR dataset because it resemble XOR function.
- here we do:
	- $f_{1} = f_{1}*f_{2}$
	- $f_{2}=f_{2}$
- then the data become like 
 ![[Pasted image 20250202172613.png]]
- now we can seperate it easily by y-axis.


**More Dataset:**
![[Pasted image 20250202173414.png]]
- here we put:
	- $f_{1}=\sin(f_{1})$
	- $f_{2}=f_{2}$
- then assign all $f_{2}$ value to -ve then we can easily seperate them.


> [!note] 
> Typical people can use multiplication of features, polynomials, trigonometric, Boolean, exponential or logarithmic transformations for making data linearly separable and even function combinations of several features

 > [!info] 
> Feature engineering is most important aspect of machine learning , deep learning automate feature engineering thats why it is so popular. e.g BOW, Tfidf etc.

# References
[[Logistic Regression Collinearity of features]]