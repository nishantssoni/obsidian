2025-02-02 17:46

Status: #code 

Tags:[[python]] [[regression]]

# Logistic Regression Code sample Logistic regression, GridSearchCV, RandomSearchCV

### Breast Cancer Dataset

The **Breast Cancer Dataset** is a classic and very easy binary classification dataset.

| **Attribute**         | **Details**                           |
| --------------------- | ------------------------------------- |
| **Classes**           | 2                                     |
| **Samples per Class** | 212 (Malignant - M), 357 (Benign - B) |
| **Total Samples**     | 569                                   |
| **Dimensionality**    | 30                                    |
| **Features**          | Real, Positive                        |

```python

from sklearn.model_selection import train_test_split, GridSearchCV
from sklearn.datasets import load_breast_cancer
from sklearn.linear_model import LogisticRegression
from sklearn.preprocessing import StandardScaler
import matplotlib.pyplot as plt
from sklearn.metrics import precision_recall_curve, f1_score, classification_report


data = load_breast_cancer() 
X_train, X_test, y_train, y_test = train_test_split(data.data, data.target, train_size=0.9, random_state=42)

scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

```
- loading the dataset which is already present in sklearn.
-  **Splitting Data:** 
	- **`train_test_split`**: Splits data into training (90%) and testing (10%) sets.
- **Standardize the Data:** 
	- Scaling helps the model converge faster because Logistic Regression is sensitive to feature magnitudes.


```python
Hyperparameter tuning tuned_parameters = [{'C': [10**-4, 10**-2, 1, 10**2, 10**4]}]
```
1. **Hyperparameter Tuning Setup:**
    - **`C`**: Regularization parameter for  Logistic Regression
        - **Smaller `C`** → Stronger regularization (simpler model).
        - **Larger `C`** → Weaker regularization (more complex model).
    - The list `[10⁻⁴, 10⁻², 1, 10², 10⁴]` tests different regularization strengths.


```python
model = GridSearchCV(
    LogisticRegression(max_iter=1000, solver='liblinear'),
    tuned_parameters, 
    scoring='f1', 
    cv=5
)
model.fit(X_train, y_train)
```

- **`GridSearchCV`**: Finds the best hyperparameters (`C` in this case) using cross-validation (`cv=5` means 5 folds).
- **`LogisticRegression(max_iter=1000, solver='liblinear')`**:
    - `max_iter=1000`: Allows more iterations to help the model converge.
    - `solver='liblinear'`: Faster and better for small datasets.
- **`scoring='f1'`**: Optimizes for the F1 score (balance between precision and recall).
- **`model.fit()`**: Trains the model with the best-found parameters.


### output
```python
print("Best Estimator:", model.best_estimator_) 
print("F1 Score on Test Set:", model.score(X_test, y_test))
```
output:
`Best Estimator: LogisticRegression(C=1, max_iter=1000, solver='liblinear')`
`F1 Score on Test Set: 0.9876543209876543`

> [!note] above C=1 which is $\frac{1}{\lambda}$ is regularization strength
>  - if $\lambda$ increases or $C$ decreases model underfit high bias
>  - f $\lambda$ decreases or $C$ increases mode overfit, high variance.


```python
y_pred = model.predict(X_test)
y_scores = model.decision_function(X_test)

# Calculate Precision-Recall values
precision, recall, thresholds = precision_recall_curve(y_test, y_scores)
f1 = f1_score(y_test, y_pred)

# Plot Precision-Recall Curve
plt.figure(figsize=(8, 6))
plt.plot(recall, precision, color='blue', linewidth=2)
plt.xlabel('Recall')
plt.ylabel('Precision')
plt.title(f'Precision-Recall Curve (F1 Score = {f1:.2f})')
plt.grid(True)
plt.show()

# Display Classification Report
print(classification_report(y_test, y_pred))
```
![[Pasted image 20250202220521.png]]

                precision    recall  f1-score   support
           0       1.00      0.94      0.97        17
           1       0.98      1.00      0.99        40
    accuracy                          0.98        57
	macro avg     0.99      0.97      0.98        57
    weighted avg   0.98      0.98      0.98        57


### Inducing more sparcity

==More Sparsity (Fewer elements of W* being non-zero) by increasing Lambda (decreasing C) ==
**more value of lambda more bias and more sparcity**

```python
import numpy as np

clf = LogisticRegression(C=0.1,solver='liblinear', penalty='l1');
clf.fit(X_train, y_train);
w = clf.coef_
print(np.count_nonzero(w))
# output : 8
```

```python
clf = LogisticRegression(C=0.0001,solver='liblinear', penalty='l1');
# output : 0
```

```python
clf = LogisticRegression(C=10,solver='liblinear', penalty='l1');
# output : 20
```



#### difference between GridSearchCV vs RandomizedSearchCV

- **GridSearchCV**:
    - Exhaustively tests all possible combinations of hyperparameters which we provide.
    - Guarantees finding the best hyperparameter set, but can be computationally expensive.
    
- **RandomizedSearchCV**:
    - Randomly samples hyperparameter combinations.
    - we only give the distribution where it select hyperparameter value randomly.
    - Faster than GridSearchCV but may not always find the best hyperparameters.
### Links
[dataset link](http://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html#sklearn.datasets.load_breast_cancer)
[article link](http://occam.olin.edu/sites/default/files/DataScienceMaterials/machine_learning_lecture_2/Machine%20Learning%20Lecture%202.html)
[logistic regression sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)
# References
[[Logistic Regression hyperparameter Search Grid search and random search]]
[[Sklearn Transform vs Fit transform]]
[[Performance measurement Precision & recall, F1-score]]
[[Solvers in Optimization Algorithms]]
[[Performance measurement Receiver Operating Characteristic Curve (ROC) curve and AUC]]