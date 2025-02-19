2025-02-19 10:06

Status: #hard  

Tags:[[svm]]

---
#### Hard margin SVM

![[Pasted image 20250218210410.png]]

**Find hyper plane that does margin maximization.**

- Let this hyper plane be $\pi: w^{T}x + b = 0$, where W is perpendicular to the hyper plane.
- then $\pi^{+},\pi^{-}$ is parallel to $\pi$ then  $w \perp \pi^{+},\pi^{-}$
	- $\pi^{+}:w^{T}x + b = 1$
	- $\pi^{-}:w^{T}x + b = -1$
	- $\text{Margin} =d= \frac{2}{||w||}$

**Objective:**
- we want to find $w^{*}, b^{*}$ which maximise the margin
	- $(w^{*},b^{*}) = argmax_{w,b}\left( \frac{2}{||w||} \right)$
**Constraint**
- for $y_{i} (w^{T}x + b) \geq 1 \text{ for all } x_{i}$
- in +ve points $y_{i}$ and $w^{T}x + b$ both 1 so the value is positive.
- and for -ve points $y_{i}$ and $w^{T}x + b$ both are -1 so value again positive.
==so it is basically constraint optimization problem of svm==

- **This works very well for linearly separable data points.**
- If the data points are mixed to some extent or some data points lie in the margin or some positive data points lie on negative side of the hyper plane then, We will never find a solution for these cases. The above constraint imposes a ==hard margin== on the SVM model. Thus the margin needs to be relaxed.
- here in hard margin svm there is no trade off because there is no loss.

#### Soft margin SVM

![[Drawing 2025-01-29 16.42.01.excalidraw]]
- Introduction of a new variable which tells how far the data point is in the opposite direction of the hyper plane. 
- This variable introduced is $\xi_{i}$ (zeta), which is equal to zero if the data point is on the correct direction of the hyper plane and is equal to the distance from the hyper plane if it is on the other side.example
	- we are seeing for the positive points ($\pi^{+}$)
	- point 1,2 $\xi_{i}=0$ 
	- point 3, $\xi_{i} = 0.5$
	- point 4, $\xi_{i}=1.5$
	- point 5, $\xi_{i}=2.5$
	- **so for point 4, $y_{i} (w^{T}x + b)=-0.5$ and if want to write in term of $\xi_{i}$ then $y_{i} (w^{T}x + b) = 1-\xi_{i} = 1-(1.5)=-0.5$**

==**so basically $\xi_{i}$ tells that the point is correctly classified or not and if it is incorrectly classified that how much the distance it is away from the correct hyperplane.==**

so the equation is 
$$
(w^{*},b^{*}) = argmax_{w,b}\left( \frac{2}{||w||} \right)
$$
if we convert argmax to argmin:
$$
(w^{*},b^{*}) = argmin_{w,b}\left( \frac{||w||}{2} \right)
$$

now using $\xi_{i}$
$$
(w^{*},b^{*}) = argmin_{w,b}\left( \frac{||w||}{2} + c*\frac{1}{n}\sum_{i=1}^{n} \xi_{i} \right)
$$
such that the constraints are
$$
y_{i} (w^{T}x + b) \geq 1-\xi_{i} \ ; \ \forall \ \xi_{i} \geq_{0}
$$

- c is hyperparameter 
- c is opposite of $\lambda$ in logistic regression
- $c*\frac{1}{n}\sum_{i=1}^{n} \xi_{i}$ avg distance of missclassified points.
- **This is an objective function which says to maximize the margin and minimize errors.**
- As C increases, tendency to make mistakes decreases, overfitting on training data, high variance. 
- As C decreases underfitting occurs, high bias. 
- The above objective formulation is for ==soft margin optimization for SVM==.

# References
[[SGD algorithm Constrained optimization & PCA]]
[[Logistic Regression Mathematic Formulation of Objective Function]]