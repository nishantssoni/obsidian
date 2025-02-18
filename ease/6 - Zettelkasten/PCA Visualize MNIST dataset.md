2025-02-18 09:53

Status: #code 

Tags:

# PCA Visualize MNIST dataset

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# loading MNIST dataset
d0 = pd.read_csv('mnist_train.csv')
# print first five rows of d0.
print(d0.head(5))
# save the labels into a variable l.
l = d0['label']
# Drop the label feature and store the pixel data in d.
d = d0.drop("label", axis= 1)
```
output:
label pixel0 pixel1 pixel2 pixel3 ... pixel8 ... pixel783
0   1     0    0   0    0      0      . ..​ 0       ... … 0


```python
# Standardizing the data(means: mean is 0 and variance is
1)
from sklearn.preprocessing import StandardScaler
standardized_data = StandardScaler().fit_transform(d)
print(standardized_data.shape)
```
output:
(42000, 784)

```python
# storing our standardized data into sample data
sample_data = standardized_data
​
#find the covariance matrix which is : (A^T * A) * 1/n
# matmul is for matrix multiplication
no_of_rows = standardized_data.shape[0]
covar_matrix = \
(1/no_of_rows) * (np.matmul(standardized_data.T,standardized_data))
print("The shape of covariance matrix = ",covar_matrix.shape)
```
output:
The shape of covariance matrix = (784, 784)

```python
# finding the top two eigen-values and corresponding eigen-vectors
# for projecting 784 DIMENSIONS Into 2 DIMENSIONS space.
from scipy.linalg import eigh
​
# the parameter 'eigvals' is defined (low value to heigh value)
# eigh function will return the eigenvalues in ascending order
# This code generates only the top 2 (782 and 783) eigenvalues because the
index starts with 0.
e_values, e_vectors = eigh(covar_matrix, eigvals=(782, 783))
​
print("Shape of eigenvectors = ",e_vectors.shape)
​
# converting the eigen vectors into (2,d) shape for easiness of further
computations
e_vectors = e_vectors.T
print("Updated shape of eigenvectors = ",e_vectors.shape)
```
output:
Shape of eigenvectors = (784, 2)
Updated shape of eigenvectors = (2, 784)

```python
# here the vectors[1] represent the eigenvector corresponding 1st principal
eigenvector
# here the vectors[0] represent the eigenvector corresponding 2nd principal
eigenvector
print(e_values)
```
output:
array([ 29.11077253, 40.69550978])


```python
# projecting the original(standardized) sample_data on the plane
# formed by two principal eigen vectors by vector-vector multiplication.
new_cordinates = np.matmul(e_vectors, sample_data.T)
print('new coordinates is :: ',e_vectors.shape,"X",sample_data.T.shape, " =
", new_cordinates.shape)
```
output:
new coordinates is :: (2, 784) X (784, 42000) = (2, 42000)


```python
# appending label to the 2d projected data here l is label which we extracted
before
new_cordinates = np.vstack((new_cordinates, l)).T
​
# creating a new data frame for plotting the labeled points.
dataframe = pd.DataFrame(data=new_cordinates, columns=("2nd_principal",
"1st_principal", "label")
print(dataframe.head())
```
output:
	2nd_principal 1st_principal label
0    -5.226445       -5.140478 1.0
1     6.032996          19.292332 0.0
2   -1.705813          -7.644503 1.0


```python
import seaborn as sn
sn.FacetGrid(dataframe,hue = "label", height=6)\
.map(plt.scatter, "1st_principal", "2nd_principal")\
.add_legend()
```
output:
![[Pasted image 20250218110127.png]]


### PCA using Scikit-Learn above code can be easily written like this:


```python
# initializing the pca
from sklearn import decomposition
pca = decomposition.PCA()
```

```python
# configuring the parameters
# the number of components or dimensions = 2
pca.n_components = 2
pca_data = pca.fit_transform(sample_data)
​
# pca_data will contain the 2-d projects of simple data
print("shape of pca_reduced.shape = ", pca_data.shape)
```
output:
shape of pca_reduced.shape = (42000, 2)

```python
# appending label to the 2d projected data here l is lable which we extracted before
pca_data = np.vstack((pca_data.T, l)).T
​
# creating a new data frame for plotting the labeled points.
pca_df = pd.DataFrame(data=pca_data,
columns=("1st_principal","2nd_principal", "label"))
print(pca_df.head())
```
output:
	1st_principal 2nd_principal label
0     -5.140444        -5.227699 1.0
1     19.292361          6.032311 0.0
2      -7.644533       -1.704946 1.0


```python
sn.FacetGrid(pca_df, hue="label", height=6).map(plt.scatter, '1st_principal',
'2nd_principal').add_legend()
plt.show()
```
output:
![[Pasted image 20250218110400.png]]
# References