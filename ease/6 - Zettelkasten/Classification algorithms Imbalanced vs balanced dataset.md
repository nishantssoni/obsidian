2025-02-20 22:21

Status:

Tags:

---
- Let say we have 2 classes
	- Dn: n data points: n1 +ve, n2 –ve pts
	- n1 + n2 = n
- If n1 ~ n2(approx) balanced dataset (example n1:n2 = 58%:42%)
- If n1<<n2 or vice versa then it is called an imbalanced dataset (example n1:n2 =5:95).
- the results will be biased towards the majority class.
---
#### Given imbalanced dataset:
- ==Undersampling:
	- n1 = 100 and n2 = 900
	- Create a new dataset with 100, n1 and n2 points randomly.
	- Here We are discarding valuable information(data loss).
	- 80% of the dataset is discarded (around 800 points of n2).
- ==Oversampling:==
	- n1 = 100 and n2 = 900
	- Create a new dataset with 900 n1 points by repeating each point 9 times,repeating more points from the minority class to make the dataset a balanced dataset.
	- Or the second method is, we can create artificial or synthetic new points through extrapolation to increase n1 from 100 to 900.
	- **Extrapolation:**
		- estimating an unknown value based on extending a known sequence of values or facts.
		- Means we can create artificial points within the range of 100 points.
	- We can also give weights to classes( class-weights) , more weight to minority classes.
	- Example :
		- if n1 = 100 and n2 = 900
		- We give n1 weight to 9 points and n2 weight to 1 point.
		- So in Knn we cout n1 to 9 NN and n2 to 1NN
		- This is the same as repeating points.
---

- Oversampling is a good idea because we are not losing any data. 
- When directly using the original imbalanced dataset, we can get high accuracy(because in the test dataset most of the points are of majority classes and we predict the majority class label which gives high accuracy) with a dumb model that predicts every query point to belong to the majority class.
- Imbalance data sets occur in the natural world often like medical diagnosis, or e-commerce where maximum people do not buy etc.
- We can use under or oversampling techniques for this. We should try to not use undersampling because throwing out data is not a good choice.



# References
[[Undersampling and Oversampling]]