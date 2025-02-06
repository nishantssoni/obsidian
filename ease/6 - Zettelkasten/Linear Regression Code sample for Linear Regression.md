2025-02-03 20:02

Status: #code 

Tags:

# Linear Regression Code sample for Linear Regression

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import StandardScaler
from sklearn.impute import SimpleImputer
from sklearn.metrics import r2_score, mean_absolute_error, mean_squared_error

# importing data
df = pd.read_csv('HousingData.csv')

# making X and Y data from the dataframe
# MEDV is the target variable
Y = df['MEDV']
X = df.drop('MEDV', axis = 1)

# splitting the dataset
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size=0.2, random_state=5)
print(X_train.shape)
print(X_test.shape)
print(Y_train.shape)
print(Y_test.shape)
```
output:
```
(404, 13)
(102, 13)
(404,)
(102,)
```
[dataset Link](https://www.kaggle.com/datasets/altavish/boston-housing-dataset?resource=download)

---

```python
# Imputer to fill NaN values with the mean of the column
imputer = SimpleImputer(strategy='mean')

# Fit on training data and transform both train and test
X_train = imputer.fit_transform(X_train)
X_test = imputer.transform(X_test)

# Scaling
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
```

---

```python
# traning the model
lm = LinearRegression()
lm.fit(X_train, Y_train)
```

---

```python
# Predictions
Y_pred = lm.predict(X_test)

# Evaluation Metrics
r2 = r2_score(Y_test, Y_pred)
mae = mean_absolute_error(Y_test, Y_pred)
mse = mean_squared_error(Y_test, Y_pred)
rmse = np.sqrt(mse)

print(f"R² Score: {r2:.4f}")
print(f"MAE: {mae:.4f}")
print(f"MSE: {mse:.4f}")
print(f"RMSE: {rmse:.4f}")
```
output:
```
R² Score: 0.7318
MAE: 3.3264
MSE: 20.9982
RMSE: 4.5824
```

---

```python
plt.scatter(Y_test, Y_pred)
plt.xlabel("Prices: $Y_i$")
plt.ylabel("Predicted prices: $\\hat{Y}_i$")
plt.title("Prices vs Predicted prices: $Y_i$ vs $\\hat{Y}_i$")
plt.show()
```
![[Pasted image 20250203200932.png]]

---

```python
delta_y = Y_test - Y_pred;
sns.set_style('whitegrid')
sns.kdeplot(np.array(delta_y), bw_adjust=0.5)
plt.show()
```
![[Pasted image 20250203201027.png]]

---

```python 
sns.set_style('whitegrid')
sns.kdeplot(np.array(Y_pred), bw_adjust=0.5)
plt.show()
```
![[Pasted image 20250203201105.png]]


# References
[[Logistic Regression Code sample Logistic regression, GridSearchCV, RandomSearchCV]]
[[Sklearn Transform vs Fit transform]]