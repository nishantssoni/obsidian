2025-01-29 08:47

Status:

Tags:

# Naive Bayes Toy example Train and test stages

![[Pasted image 20250129084804.png]]
- Above is the dataset with four categorical data f1, f2, f3 and f4.
- And C the response name Play with two categories yes and no.
- Now we want to compute play ={yes, no} given the x, so we use bayes theorem for that as follows:
	- P(C| f1, f2, f3, f4) = P(f1|C) * P(f2|C)* ......*P(C)
	- So we get all the values by counting.
	- ![[Pasted image 20250129084924.png]]
	- Similarly for all four features and We also calculate P($Class_{Play}=Yes$) and P($Class_{Play}=No$) 
	- ![[Pasted image 20250129085035.png]]
	- All this we compute in the ==Training Phase.==
- **During training**
	- Time complexity: O(ndc) through optimization O(n)
	- Space complexity: O(dc)
	- d is the features and c is classes,These probabilities are proportional
- P(class = No|x’) > P(class = Yes|x’); thus the prediction will be class = No for x1 data Point.
- **During Testing**:
	- Test Time complexity: O(dc)
- kNN space complexity: O(nd)
- ==As compared to kNN Naïve Bayes is space efficient at run time, we can have low latency applications.==

Now Let’s say, x’=(Outlook=Sunny, Temperature=Cool, Humidity=High, Wind=Strong) so the Yq is :
![[Pasted image 20250129085421.png]]
- Likelihood focuses on the relationship between features and classes: P(Feature∣Class).
- Probability includes both prior information (before observation) and posterior calculations (after observation).

#### Link
<a href="https://web.archive.org/web/20221202040337/https://shatterline.com/blog/2013/09/12/not-so-naive-classification-with-the-naive-bayes-classifier/">Full blog</a>
# References