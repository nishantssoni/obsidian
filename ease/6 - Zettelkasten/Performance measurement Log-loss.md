2025-02-20 21:46

Status:

Tags: [[maths]]

---

- Smaller the better ( all loss function we tried to minimize it.)
- Binary classification problem: Log Loss uses actual probability scores
- Log – loss: average negative logarithm of probability of correct class label.

$$
\text{Log Loss} = -\frac{1}{n}\sum((y_{i}* \log(\pi)) + ((1-y_{i})* \log(1-\pi)))
$$
- n is number of points
- pi is probabilistic score
- yi is actual class label
- If your class label is 1 then (1 − 𝑦𝑖) term become zero and only first term remains, similarly if your class label is 0 then the first term become zero.

| $x_{i}$ | $y_{i}$ | $\pi$ |
| ------- | ------- | ----- |
| $x_{1}$ | 1       | 0.9   |
| $x_{2}$ | 1       | 0.6   |
| $x_{3}$ | 0       | 0.1   |
| $x_{4}$ | 0       | o.4   |
- In the above table the pi is the probabilistic score of point to be class 1.
- -log(0.9) = 0.0457
- -log(0.6) = 0.22
- -log(1- 0.1) = -log(0.9) = 0.0457
- -log(1- 0.4) = -log(0.6) = 0.22
---

- So the smaller the log loss the better it is.
- Log loss takes care of mis-classifications.
- This model is penalizing even for small deviations in probability scores. e.g for 0.9 it is 0.045 but for 0.6 it is 0.22
---

For multi class classification:

$$
\text{Log Loss} = -\frac{1}{n}\sum_{i=1}^{n}\sum_{j=1}^{c} (y_{ij} * \log(p_{ij}))
$$
- log(pij) probability that xi belongs to class j
- C is number of class labels
- yij is 1 if xi belong to class j else 0
- **If we put c =2 in above we get the formula of log loss for binary class.**
- article
	- [part 1](https://medium.com/usf-msds/choosing-the-right-metric-for-machine-learning-models-part-1-a99d7d7414e4)
	- [part 2](https://medium.com/usf-msds/choosing-the-right-metric-for-evaluating-machine-learning-models-part-2-86d5649a5428)

# References