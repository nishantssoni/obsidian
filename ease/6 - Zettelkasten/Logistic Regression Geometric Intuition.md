2025-01-24 23:40

Status:

Tags: [[regression]] [[ml_algorithm]]

# Logistic Regression Geometric Intuition



Logistic Regression is a classification technique.  
Logistic Regression can be interpreted in terms of geometry, probability, and the loss function.  
If the data is linearly separable or almost linearly separable (a hyperplane can separate the data points into two classes), then:

## Equation of the plane:
$$ W^T x_i + b = 0 $$

Where:
- $W$ is the normal vector and $b$ is the intercept of the plane.
- $W$ and $x$ are vectors in a $d$-dimensional space, and $b$ is a scalar.
- If the hyperplane passes through the origin, then $b = 0$, and the equation becomes:  
  $$ W^T x = 0 $$

Now, the assumption of Logistic Regression is:  
- In the data points, the classes are almost or perfectly linearly separable.

## Task:
Find the plane that best separates the data points, or in other words, find $W$ and $b$.

![[image.J5GC12.png]]
### Other model assumptions:
- **kNN**: Neighborhood similarity  
- **NB**: Conditional Independence  
- **Logistic Regression**: Linearly separable  

Negative data points are labeled as -1 instead of 0, so $y_i = \{1, -1\}$.

## Distance of a point from the hyperplane:
$$ d_i = \frac{W^T x_i}{\|W\|} $$

If $W$ is a unit normal vector to the hyperplane, then $\|W\| = 1$, and the equation becomes:  
$$ d_i = W^T x_i $$

Now, we have a classifier where if the data point is in the same direction as the normal vector, it belongs to the positive class; otherwise, it belongs to the negative class.

### Here are two cases:

#### Case 1 (Correctly classified):  
$y_i * W^T x_i > 0$
- If $y_i = +1$, then $W^T x_i > 0$.
- If $y_i = -1$, then $W^T x_i < 0$.

#### Case 2 (Incorrectly classified):  
$y_i * W^T x_i < 0$
- If $y_i = +1$, then $W^T x_i < 0$.
- If $y_i = -1$, then $W^T x_i > 0$.

For all data points:
- If $y_i * W^T x_i > 0$, the data point is correctly classified.
- If $y_i * W^T x_i < 0$, the data point is incorrectly classified.

The machine learning model should have a minimum number of misclassifications. Thus, the goal is to find $W$ (the plane) that maximizes:  
$$ \sum_{i=0}^n y_i * W^T x_i $$

The new $W$ is:  
$$ W' = \arg \max \left( \sum_{i=0}^n y_i * W^T x_i \right) $$

> [!info] 
> There are three interpretation we can use to solve Logistic regression
> 1. Geometric intuition
> 2. Probablity intuition
> 3. Loss minimization


# References