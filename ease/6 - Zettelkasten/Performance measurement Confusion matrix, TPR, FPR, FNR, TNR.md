2025-02-20 22:01

Status: #important

Tags:

---
- In a binary classification problem we have two classes.
- a confusion matrix can be built with column vectors as predicted class labels and row vectors as actual class labels.
- **Confusion matrix cannot process probability values.**
---
![[Pasted image 20250220220303.png]]

- a = actual 0 and predicted 0
- b = actual 1 and predicted 0
- c = actual 0 and predicted 1
- d = actual 1 and predicted 1

---
- For Multi class classification, we will have a matrix of size cxc where c is the number of classes.
- If the model is sensible, then the principal diagonal elements will be high and the off-diagonal(upper and lower triangular matrix) elements will be low.
---
#### TN,FN,FP,TP:
- a = True Negatives(Predicted Negatives truly)
- b = False Negatives(Predicted Negatives falsely)
- c = False Positives(Predicted positive falsely)
- d = True Positives(Predicted positive truly)
- ![[Pasted image 20250220220529.png]]
- N : total number of Negative
- P : total number of positives.
- Total number of points is N + P.

---

#### TPR, TNR, FPR, FNR
- $\text{TPR(true positive rate)} = \frac{TP}{P} = \frac{TP}{(TP + FN)}$
	- In binary classification, the True Positive Rate (TPR), also known as Sensitivity or Recall, represents the proportion of positive instances (e.g., spam emails) that are correctly identified by the model as positive. TPR can be thought of as the "benefits" or "advantages" of a model's performance in certain applications.
- $\text{TNR(true Negative rate)} = \frac{TN}{N} = \frac{TN}{(TN + FP)}$
- $\text{FPR(False positive rate)} = \frac{FP}{N} = \frac{FP}{(TN + FP)}$
	- You can think **FPR as cost**.
	- The False Positive Rate (FPR) is an important metric in binary classification, especially when dealing with scenarios where the consequences of misclassifications have real-world costs or impacts.
	- example: 
		- if you misclassify 20 legitimate (not spam) emails as spam, those are False Positives. This means you falsely identify non-spam emails as spam. This can lead to several negative consequences like Customer Dissatisfaction, Business Losses etc.
- $\text{FNR(False Negative rate)} = \frac{FN}{P} = \frac{FN}{(TP + FN)}$

---
#### Example
![[Pasted image 20250220221201.png]]

- N = 900, P = 100 and N+P = 1000
- And after testing we get the value of TN,TP,FN,FP respectively shown in figure.
- TPR = (94 / 100) * 100 = 94%
- TNR = (850 / 900) * 100 = 94.4%
- FPR = (50 / 900) * 100 = 5.6%
- FNR = (6 / 100) * 100 = 6%
- **In the above figure we see that the confusion matrix also works for an imbalance dataset.**
- **Model is good if TPR, TNR are high and FPR, FNR are low.**
---

- A dumb model makes one of TPR or TNR = 0.
- The condition for which TPR, TNR, FPR and FNR should be considered or which is more important among these four values depends on the domain.
- Example : for cancer diagnosis:
	- We don't want to miss a patient who has cancer,so we have to make FNR(actual 1 but predicted 0) close to zero and FNR is most important in cancer detection.
	- And after FNR we also have to make TNR and TNR high.
	- For FPR(actual 0 predicted 1) if a patient does not have cancer and our model predicts it has cancer then we can send the patient for further tests, but a patient cannot be left untreated due to False Negatives(FNR).
	- Here FNR is most important so which value to choose is domain specific.

# References
[[Performance measurement Precision & recall, F1-score]]