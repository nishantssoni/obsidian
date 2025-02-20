2025-02-20 21:04

Status:

Tags:

---

- Outliers at test time are taken care of by Laplace smoothing.
- And in train time if a word occurs less frequently then some threshold then discard that word or you can do laplace smoothing which impacts less frequent words more and make the probability uniformly distributed(equally likely).

# References
[[Classification algorithms Impact of Outliers]]