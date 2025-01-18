2025-01-19 00:12

Status:

Tags:[[numpy]] [[statistics]]

# Numpy Statistics Operations


### Statistics Operations in NumPy

NumPy provides a variety of functions for performing statistical operations on arrays. These functions allow you to calculate measures such as the mean, median, standard deviation, and more, across entire arrays or specific axes.

#### 1. **Mean**

- The `mean()` function computes the average of all elements in an array.

Example:

```python
x = np.array([1, 2, 3, 1])
x.mean()  # Output: 1.75
```

#### 2. **Median**

- The `median()` function returns the middle value in the sorted data. For an even number of elements, it returns the average of the two middle elements.

Example:

```python
np.median(x)  # Output: 1.5
np.median(y, axis=-1)  # Output: array([2., 5.])
```

Here, `axis=-1` computes the median along the last axis (rows, in this case).

#### 3. **Standard Deviation (Population)**

- The `std()` function computes the standard deviation. By default, it calculates the population standard deviation (not sample).

Example:

```python
x.std()  # Output: 0.82915619758884995
```

#### 4. **Loading Data**

- You can load data from a file (e.g., 'populations.txt') into a NumPy array using `np.loadtxt()`. This is useful for working with large datasets.

Example:

```python
data = np.loadtxt('populations.txt')
data
# Output:
array([[  1900.,  30000.,   4000.,  48300.],
       [  1901.,  47200.,   6100.,  48200.],
       [  1902.,  70200.,   9800.,  41500.],
       … ])
```

#### 5. **Data Transposition**

- You can transpose the matrix to convert columns into variables for easier manipulation. This is done using `.T`.

Example:

```python
year, hares, lynxes, carrots = data.T  # Transpose the matrix and unpack columns
print(year)
# Output: [1900. 1901. 1902. ...]
```

#### 6. **Population Statistics**

- You can extract specific columns (like population data) and perform calculations on them.

Example:

```python
populations = data[:, 1:]  # Take all rows but columns from 1 onward
populations.std(axis=0)  # Standard deviation for each column (species)
# Output: array([20897.90645809, 16254.59153691, 3322.50622558])
```

#### 7. **Finding the Highest Population**

- To find which species had the highest population each year, use `np.argmax()` to find the index of the maximum value along a specific axis.

Example:

```python
np.argmax(populations, axis=1)  # Output: array([2, 2, 0, 0, 1, 1, 2, 2, 2, 2, 2, 2, 0, 0, 0, 1, 2, 2, 2, 2, 2])
```

This function will return the index of the maximum value for each year, indicating which species (0: hares, 1: lynxes, 2: carrots) had the highest population each year.



# References