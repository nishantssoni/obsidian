2025-01-29 08:58

Status:

Tags:

# Naive Bayes Laplace or Additive Smoothing

- It solves the problem of multiplication by zero to the new unseen word.
- At the end of training all the likelihoods and priors are computed. 
- At test time:
	- Say we find a new word for which likelihood is not available.
	-  If the new word w’ is not present in training then we can’t have P(w’ | y).
	- We will use Laplace smoothing (not Laplacian smoothing) as the word is not present in training data ideas such as making its likelihood as 0 or 1 or 0.5 is not right, thus we will add a smoothing value to the numerator and denominator for likelihood probability of the new word.
---

**P(W’|y=1) = (0 + α) / (n1 + αk)**:
- N1 = # of data points for y = 1
- Smoothing coefficient, α != 0; generally = 1
- k = number of unique values, w’ can take (for a categorical feature it can k = # of unique categories) here k = 2 because of {0,1}.
- When α = large, the likelihood will be evenly distributed across all the categories and we can say that, we are going towards a ==uniform distribution.==
- When we make α = large,we generally make a bias by thinking that there is w’ likelihood to be 0 or 1 so we assume 0.5.
---
- Laplacian smoothing is applied to all words in training data and also to new words that occur in test data.
- $\frac{𝑛𝑜 \ 𝑜𝑓 \ 𝑑𝑎𝑡𝑎 \ 𝑝𝑜𝑖𝑛𝑡𝑠 \ 𝑤𝑖𝑡ℎ \ 𝑤_{i} 𝑎𝑛𝑑 \ 𝑦 = 1 + α}{𝑛𝑜 \ 𝑜𝑓 \ 𝑑𝑎𝑡𝑎 \ 𝑝𝑜𝑖𝑛𝑡𝑠 \ 𝑤𝑖𝑡ℎ \ 𝑦 = 1 + α𝑘}$
- We have additive smoothing and generally 1(called add one smoothing) additive smoothing is applied, that is Laplace smoothing with α = 1.
- ![[Pasted image 20250129090421.png]]
- ==IF Model is underfitting decrease your alpha and if it is overfitting increase
your alpha.==

# References