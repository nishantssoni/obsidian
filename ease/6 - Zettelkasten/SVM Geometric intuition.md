2025-02-18 20:16

Status:

Tags: [[svm]]

---
## SVM Geometric intuition

SVM – Popular Machine Learning Model – classification and regression problems

Let data points be as:

![[Pasted image 20250218210247.png]]
The data points can be separated with many hyper-planes. Say, with

- In logistic regression, if a data point is very close to the hyper plane, then the probability of the point belonging to a class is very close to 0.5. For points away from hyper plane the probability will be close to 1.

==The objective or key idea about SVM will be to separate the data points with a hyper plane which is as far as possible from the data points.==

- π2 is better than π1 as the hyper plane is as far as possible from all data points. Thus, π2 can be taken as a margin maximizing hyper plane.


![[Pasted image 20250218214940.png]]
- Take π+ and π- parallel to π2 such that it touches first data point of the +ve and -ve group. 
- We get a margin and with SVM we maximize the width of this margin.


**Objective of svm: 
- find π such that distance between (π+, π-) called margin is maximum**
- With this we will have lesser misclassifications and better generalization (margin increases).

**Support Vector:
- Say we have the margin maximizing hyper plane π, and we have π+ and π-, the data points through which these margin planes pass through are called support vectors. We have two support vectors in the following plot.

![[Pasted image 20250218210410.png]]

For classification we will use π, the margin maximizing hyper plane.

#### Alternative Geometric Intuition of SVM: Using Convex hulls:

![[Pasted image 20250218210444.png]]

- Convex hulls is the smallest polygon where all the points are inside or in the polygon. And while connecting to two points with a line the line should not go outside the polygon.

![[Pasted image 20250219100601.png]]

- Build smallest convex hulls for each set of data points, find the shortest line connecting these hulls.
- and draw a perpendicular bisector to this line to get the margin maximization hyper plane.
 
## References