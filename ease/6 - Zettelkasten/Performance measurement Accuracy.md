2025-02-20 22:14

Status:

Tags: 

---
**Task: Measure performance of ML models**

- Accuracy:
	- ratio of number of correctly classified points to total number of points.
	- It lies between 0-1.
- Case 1:
	- if we have an imbalanced dataset, with a dumb model we can get high accuracies.
	- Accuracy cannot be used for imbalanced datasets.
	- Example let we have a data which has 90% -ve points and 10% positive points and our dumb model classifies every point to be -ve so in test data it shows that our model has 0.9 accuracy.
- Case 2:
	- ![[Pasted image 20250220221745.png]]
	- In above figure:
		- X is query point
		- y is actual class label
		- m1 and m2 values are the probabilistic score of a point being 1.
		- m1’ and m2’ are the corresponding prediction value of the models m1 and m2.
		- So if we see the accuracy of both models from m1’ and m2’ then both models have the same accuracy of 1.
		- But we know from the probabilistic score that model m1 is better so we cannot deduct which model is better.
---
- an inferior model predicts probability values far from true labels (near 0.5 predictions) while a powerful model predicts probability values nearer to true Labels (far from 0.5 predictions).
- accuracy can say that an inferior model is working similar to a powerful model.
- Thus accuracy cannot give an idea whether a model is inferior or powerful.
- **So it is not a good idea to use accuracy in the case of a model that returns a probabilistic score.**
	





# References
