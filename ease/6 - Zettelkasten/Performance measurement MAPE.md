2025-02-20 21:55

Status:

Tags:

---
- MAPE stands for Mean Absolute Percentage Error. It is a performance metric used to evaluate the **accuracy of a regression model**, especially when dealing with time series or forecast data. MAPE measures the percentage difference between the actual and predicted values, making it useful for understanding relative errors.
- $\text{MAPE} = \sum \frac{actual-predicted}{actual} * \frac{1}{n}$ 
	- Σ represents the sum of absolute percentage errors for all data points.
	- (actual - predicted)| denotes the absolute difference between the actual and predicted values for each data point.
	- actual is the true (actual) value of the target variable.
	- predicted is the predicted value of the target variable.
	- N is the total number of data points.
- The MAPE is expressed as a percentage, and it gives an idea of how well the model's predictions match the actual values relative to the actual values themselves.
- **A lower MAPE indicates better accuracy of the model.**
---
Here's how you can use MAPE in scikit-learn:
```python
from sklearn.metrics import mean_absolute_percentage_error
mape = mean_absolute_percentage_error(y_true, y_pred)
```
- Remember that MAPE may not be well-defined for data points where the actual value is zero. In such cases, you may consider using alternative metrics like Mean Squared Percentage Error (MSPE) or other performance measures depending on the specifics of your problem.
---
- You can also use modified MAPE like WMAPE
	- [article](https://en.wikipedia.org/wiki/Mean_absolute_percentage_error)
	- [youtube](https://www.youtube.com/watch?v=ly6ztgIkUxk)



# References
