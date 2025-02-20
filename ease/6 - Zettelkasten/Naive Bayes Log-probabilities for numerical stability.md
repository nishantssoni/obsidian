2025-02-20 20:55

Status:

Tags:

---
- We have probability values which are bound between 0 and 1.
- While the probabilities are multiplied the result will be extremely low which will affect our model performance and result interpretation, we will also land in rounding up errors for low decimal values which make errors.
	- Eg: 0.2 * 0.001 * 0.03 * ………
- We will take a logarithm of probabilities to avoid the problems of multiplying values between 0 and 1.
	- log(0.2 * 0.001 * 0.03 * ………) = log(0.2) + log(0.001) + ….
	- And log is a monotonic function so we can compare log probability instead of normal probability.




# References