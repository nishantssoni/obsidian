2025-01-31 15:58

Status:

Tags:

# Classification algorithms Feature importance & Forward Feature Selection


- Important features:
	- Features that are useful for the machine learning model in making predictions.
	- This improves model interpretability.
	- Feature importance allows us understand a model better;
- ==kNN does not give feature importance by default.==
- Forward feature selection:
	- Given a model f through forward feature selection we can use the model itself to get feature importance.
	- Given a high dimensionality dataset we want to reduce dimensionality to make things easier for computations (curse of dimensionality).
	- One way is to use PCA/ tSNE, but PCA and tSNE care about preserving distances and do not care about classification tasks, but for classification tasks using forward feature selection we can discard less important features.


- Forward feature selection working:
	- Given a dataset of d features.
	- First make an empty set.
	- use each(only one) feature at a time to train an ML model, the performance(accuracy) of the model is noted with respect to each(only one) feature.
	- The feature that gives highest accuracy is selected, say f9 is selected then we add f9 to set {f9}.
	- Retrain the model with remaining features where f9 is already selected.
	- By selecting f9 and the train for f1,f2,f3…..fn(one at a time).
	- Let's say we get f9 + f6 highest accuracy.
	- Then add f6 to the set { f9, f6 }.
	- Repeat these steps up to d time (d is the iteration or the number of features which you want to keep).
	- This stage wise concatenation of features to gain high performance from the model is called forward feature selection.

> [!note] 
>  At **first stage** we have the second best feature(let set f2 which is after f9) it may happen that this feature in combination with the first best feature may not provide good performance, so at each stage we check **that given that a feature or set of features are selected previously as best features we now explore for features that add most value to model performance.**

- ==We can have a backward selection, where we try to remove the feature(one at a time) that results in the lowest drop in performance of the model.==

Disadvantage:
-  At any iteration we are training the ML model, time complexity is very high.

Advantage:
- Forward and backward selection models are model agnostic which means it doesn't care which model you choose.

# References
[[Classification algorithms Curse of dimensionality]]