2025-02-02 13:44

Status:

Tags:[[regression]]

# Logistic Regression Real world cases


- Decision surface:
	- Linear Hyperplane
- Assumption:
	- data is linearly separable or almost linearly separable.
- We also have good interpretability.
- Imbalanced data:
	- Upsampling or down sampling
	- with imbalanced data we will have incorrect hyper planes that can optimize the loss function where the hyper plane can make all the data points lie on one side optimizing the loss function for majority class.
- Outliers:
	- due to sigmoid function the impact is less.
	- We can compute $W^{*}$ from $D_{train}$ through training and generate distances through $W^{T}x_{i}$
	- the points that have large distances are outliers can be removed to make $D_{train}$ free from outliers.
	- the model is retrained on the outlier free dataset to get final Weight vector.
- Missing values:
	- mean, median or model imputation.
- Multi class classification:
	- people generally do One Vs Rest.
	- But there is extension for multiclass example Max entropy/Softmax/Multinomial LR models
- similarity matrix: 
	- Extension of LR, Kernel LR (SVM) can be trained on similarity matrix.


- Best case:
	- Data is linearly separable, low latency, faster to train.
	- high dimensionality (higher chance that data is linearly separable and we can use L1 regularization)
- Worst case:
	- Non linear data.
# References
[[Logistic Regression Feature importance and model interpretability]]
[[Logistic Regression How does imbalance data impact LR geometrically]]
[[Naive Bayes Similarity or Distance matrix]]
