2025-02-20 21:02

Status:

Tags:

---

The majority class has advantage over minority class while comparing 
probabilities so we do use some technique to avoid this as follows:
- We can use upsampling or downsampling.
- drop prior probabilities
	- If +ve point is 900 and -ve point is 100
	- P(y=1) * P(w1|y=1) * ……..
	- P(y=0) * P(w1|y=0) * ……..
	- So here, P(y=1) = 0.9 and P(y=0) = 0.1
	- So P(y=1) always has advantage so we drop P(y=1) and P(y=0).
- There is modified Naïve Bayes to account for class imbalance (less used)
When laplace smoothing is applied: alpha impacts more for minority class.
We can have different α values for different classes.(its a hack)
To conclude this Naive Baise is Impacted by imbalance data in two ways:
- Impact the priors
-  Impact the likelihood ratios when using laplace smoothing.

# References