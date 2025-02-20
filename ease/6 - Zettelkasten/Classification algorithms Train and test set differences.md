2025-02-20 22:31

Status:

Tags:

---
- The main difference between training data and testing data is that training data is the subset of original data that is used to train the machine learning model, whereas testing data is used to check the accuracy of the model. So both have almost similar distribution.
- Given a dataset we had random splitting or time based splitting.
	- For example in e-commerce we can have new products getting added after some time or old products removed.
	- So in time based splitting the old training data cannot seen the new product review.
	- So training and testing data distribution changes fundamentally.
	- Train and CV error can be low because we use training data in it.
	- But we can have test error high because the decision boundary changes in test data.
- We need to check the distribution of train and test data sets for any change over time.
- For checking if the train and test dataset is different distribution we use a simple hack.
	- We split Dn in two parts
	- Dtrain (xi, yi) and Dtest (xi, yi)
	- Now we make new data set using old one
	- We make a Dn’ data set and split into two parts where
	- Dtrain(xi’, yi’) = ((xi, yi), 1)
		- xi’ = (xi,yi) of Dn train and yi’ = 1
	- Dtest(xi’, yi’) = ((xi, yi), 0)
		- xi’ = (xi,yi) of Dn test and yi’ = 0
	- Train a binary classifier on Dn’.
	- **If the accuracy is high then Dtrain and Dtest are dis-similar** because the data is easily separable with high accuracy which means both distributions are different .
	- **If the accuracy is low then Dtrain and Dtest are similar** which means that both points are overlapping or randomly distributed within the same region which make both distributions similar and points are hard to separate.
	- **If accuracy is high in Dn’ then both distributions are fundamentally different and we get test accuracy errors very high in Dn.**
	- **If accuracy is low in Dn’ then both distributions are fundamentally same then we can do any classifier algorithm is Dn.**
- To get Dtrain and Dtest follow the same distribution (stable data) we will need to get small accuracy in Dn’.
- [Article](https://medium.com/@praveenkotha/how-to-find-whether-train-data-and-test-data-comes-from-same-data-distribution-9259018343b)




# References