2025-02-02 22:08

Status:

Tags:

# Performance measurement Receiver Operating Characteristic Curve (ROC) curve and AUC

![[Pasted image 20250202220906.png]]
- It was developed by electronic and radio engineers during World War II to predict how well the missiles are working.
- It is used for binary classification.
- Sort the data frame by descending order of predicted class labels (y_hat).
- The sorting is done by observing any score value of the predicted class.
- Here we are using a probabilistic score for sorting the class label.
- Thresholding (𝛕):
	- Now we take the top point as 𝛕1, which has the probabilistic score of 0.95.
	- Mark 1 to all points that have a greater or equal score.
	- Deduce TPR and FPR from that threshold.
	- Now again, we take the second top point 𝛕2 and do the same for all points.
	- For n points, we have n thresholds.
	- For every threshold value, we compute TPR and FPR.
	- We can now have n thresholds with n TPR and FPR.

![[Pasted image 20250202221004.png]]
- These TPR and FPR can be plotted on a TPR vs FPR graph, which generates a curve called the Receiver Operating Characteristic Curve.
- The area under this curve is called AUC.
- AUC ranges from 0 to 1.
- 1 is ideal.
- AUC can be high even for a dumb model when the dataset is imbalanced.
- AUC is not dependent on the predicted value scores; rather, it considers the ordering, so the score of the predicted value (like the probabilistic score) is only used for sorting. It does not affect the curve unless the order changes.
- ==If two models give the same order of predicted values, then AUC will be the same for both models.==
- ==AUC for a random model is 0.5.==
- Preferred AUC is a value > 0.5.
- AUC between 0 and 0.5 implies that the predictions are reversed or there are some errors. The best way to solve this issue is to reverse the predicted value (for 0, return 1, and vice versa).
- If the predictions are reversed, then the new AUC value will be 1 – old AUC. (e.g., if the AUC of the old model is 0.2, then after reversing the prediction value, we get a 0.8 AUC score, which is good.)
- We know that TPR is like benefit, and FPR is like cost, so ==TPR vs FPR is like a benefit vs cost graph.==


# References