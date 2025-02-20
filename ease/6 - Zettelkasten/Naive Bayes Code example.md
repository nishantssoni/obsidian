2025-02-20 21:12

Status: #code 

Tags: 

---
- Sklearn Naïve Bayes module.
- Different ML algorithms are implemented by just changing a single line of code.
- In ML the task is to understand the applications of different algorithms.
![[Pasted image 20250220211344.png]]

```python
class sklearn.naive_bayes.BernoulliNB(*, alpha=1.0, force_alpha=True, binarize=0.0, fit_prior=True, class_prior=None)
```

- alpha: 
	- Smoothing parameter to handle zero probabilities; higher values add more smoothing.
- force_alpha: 
	- Ensures smoothing is applied even if alpha is set to 0.
- binarize: 
	- Threshold for converting features to binary; values above it become 1, below or equal become 0.
- fit_prior:
	- Determines whether class prior probabilities are learned from thetraining data.
- class_prior:
	- Allows manual specification of class prior probabilities; estimated automatically if set to None.



# References