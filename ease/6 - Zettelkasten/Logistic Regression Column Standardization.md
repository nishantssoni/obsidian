2025-01-29 17:06

Status:

Tags: [[regression]]

# Logistic Regression Column Standardization


==we use Mean centering (numerator) and scaling(denominator) just like we used in kNN==
- $x_{ij}' = \frac{x_{ij} - \mu_{j}}{\sigma_{j}} \ where \ \mu \ is \ mean  \ and \ \sigma \ is \ std \ deviation$
- In logistic regression it is also mandatory to perform column standardization as we are using distances to compute the weight vector and the scale of features impacts the distance values.

# References
[[Features Standardization]]