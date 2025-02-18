2025-02-18 11:16

Status:

Tags:

# PCA PCA for dimensionality reduction visualization
==It is using MNIST dataset==


```python
# let we can take all 784 dimensions
pca.n_components = 784
​
# now our principal component is
pca_data = pca.fit_transform(sample_data)
print(pca_data.shape)
```
output:
(42000, 784)

```python
# pca.explained_variance_ is all the eigenvalues in descending order
for i in range(4):
	print(pca.explained_variance_[i])
```
output:
40.69647874534515
29.11146565722667
26.78333709864516
20.814719425177486

```python
# sum of eigenvalues
sum_of_eig_values = np.sum(pca.explained_variance_)
​
# compute percentage of each eigenvalue
percentage_var_explained = pca.explained_variance_ / sum_of_eig_values

for i in range(4):
	print(percentage_var_explained[i])
```
output:
0.057479533589781764
0.04111691034899995
0.03782867146912825
0.02939862123816347

```python
# cumulative sum to find how many eigenvalues needed to get our desire
variance
cum_var_explained = np.cumsum(percentage_var_explained)

for i in range(4):
	print(cum_var_explained[i])
```
output:
0.057479533589781764
0.09859644393878171
0.13642511540790997
0.16582373664607344


```python
# Plot the PCA spectrum
plt.figure(1, figsize=(6, 4))
plt.clf()
plt.plot(cum_var_explained)
plt.axis('tight')
plt.grid()
plt.xlabel("n_components")
plt.ylabel("Cumulative_explained_variance")
plt.show()
```
output:
![[Pasted image 20250218112058.png]]


- **Now from the above figure we can say that for obtaining 90% of variance we can reduce 784 dimensions to 200(approx) dimensions.**
- **And 784 - 200 = 484 dimensions only contain 10 % of variance.**
- **Note: 200 dimensions is our first 200 principal dimensions which means the largest 200 eigenvalues.**

# References
[[PCA PCA for dimensionality reduction (not visualization)]]
[[PCA Visualize MNIST dataset]]