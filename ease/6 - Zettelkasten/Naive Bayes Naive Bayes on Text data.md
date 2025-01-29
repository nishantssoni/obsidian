2025-01-29 08:55

Status:

Tags:

# Naive Bayes Naive Bayes on Text data

- Naive Bayes is applied successfully to text data.
- Task: Given text, compute probability of the text belonging to a class.
	- Let assume that after text preprocessing like stopword, stemming, ngrams etc. we get a list of texts.
	- And let's assume that there is binary class 0, 1.
	- So P(y=1| text) = P(w1, w2,....wn | y=1) (bayes theorem)
	- P(y) * P(w1|y) * …… * (wn | y) Similarly we can get for y=0.
- So for spam filters and polarity of review or especially text classification Naive bayes is a very good baseline(bench mark) algorithm.
- all other algorithms are compared with Naive Bayes performance.

# References