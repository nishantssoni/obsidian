2025-02-03 16:23

Status:

Tags: [[regression]]

# Linear Regression Real world Cases

For imbalance data:
- upsampling, down sampling
- **No problem of imbalanced data**

Feature Importance and Interpretability: 
- same as for Logistic Regression
- we can use weight vector elements if the data does not have multi collinear features.
- we can use L1 or L2 regulaizer to get interpretability
	- if we increase $\lambda$ the the less important feature become saprse and we filter the top features from there.

Outliers:
- In logistic regression we have sigmoid function that is squashing and limiting the impact of outliers.
- In Linear Regression we will have squared loss, to remove outliers we can compute distances of a Hyperplane that best fitted on the training set.
- the data points that are very far from the hyper plane are removed and the hyper plane is regenerated to fit the outlier free data set, iterable up to satisfaction.
- Outliers impact the model heavily, this technique of iterated removal of outliers from model training is called ==RANSAC==

# References
[[Logistic Regression Real world cases]]
[[RANSAC]]