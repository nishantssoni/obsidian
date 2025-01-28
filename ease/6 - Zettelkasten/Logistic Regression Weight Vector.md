2025-01-25 14:32

Status: #hard 

Tags:[[regression]] [[vector]]

# Logistic Regression Weight Vector

in logistic regression, a "weight vector" refers to ==a collection of numerical values, represented as a vector, that signifies the importance of each feature in the input data when predicting the target variable==; essentially, each element in the vector represents how much influence a corresponding feature has on the final prediction, allowing the model to weigh different features accordingly during the classification process. 

Key points about weight vectors in logistic regression:
- **Representation:**
    The weight vector is usually denoted by "w" and is a column vector where each element corresponds to a feature in the data set. 
    
- **Impact on prediction:**
    A higher absolute value in the weight vector indicates a stronger influence of that feature on the prediction. 
    
- **Learning process:**
    During training, the model learns and updates the values of the weight vector through optimization algorithms like gradient descent, aiming to find the best combination of weights that maximizes the accuracy of the prediction. 
    

> [!example] 
>  Imagine predicting whether a customer will purchase a product based on features like age, income, and education level. The weight vector would contain values for each of these features, where a high weight for "income" would mean that income plays a significant role in determining the purchase probability. 


### optimization problem
- we want to solve the optimization problem which is we want to minimize the $W^{*}$ 
- $W^{*}=argmax_{w}\left( \sum_{i=1}^{n} \frac{1}{1+\exp(-y_{i}W^{T}x_{i})} \right)$
- imagine we get the optimal $W^{*}$  this optimal $W^{*} \ is \ called \ weight \ vec tor$
- weight vector is also a d-dimensional data just like x 
### Geometric intuition Weight vector (W)
- here W vector is the optimal weight vector normal to a hyper plane that separates data points into classes where positive data points are in the direction of W
![[Pasted image 20250125144736.png]]

- if the point is on the hyper plane we cannot determine the class of the query point.
**Probabilistic interpretation:**
- $P(y_{q} = +1)$ = $sigmoid(W^{T}x_{q})$  (Remember the need for sigmoid function: squashing)

> [!important] 
>  **Interpretation of Weight vectors:**
>  Case 1:
>  - if $W_{i} = +ve$ then if $X_{qi}$ increases $W_{i}x_{qi}$  increases, $sigmoid(W^{T}x_{q})$ increases, then $P(y_{q} = +1)$ increases.
> 
> Case 2:
> - If $W_{i} = -ve$  then if $X_{qi}$ increases $W_{i}x_{qi}$ decreases, $sigmoid(W^{T}x_{q})$ decreases, then $P(y_{q} = +1)$  decreases and then $P(y_{q} = -1)$ increases.

# References
[[Logistic Regression Mathematic Formulation of Objective Function]]