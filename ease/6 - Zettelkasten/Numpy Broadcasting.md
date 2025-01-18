2025-01-19 00:17

Status:

Tags:[[numpy]] [[broadcasting]]

# Numpy Broadcasting

### Broadcasting in NumPy

Broadcasting is a powerful feature in NumPy that allows you to perform element-wise operations on arrays of different shapes. When performing operations like addition, subtraction, or multiplication, NumPy automatically adjusts the shapes of arrays to make them compatible, so that element-wise operations can be performed.

![[02.05-broadcasting.png]]

#### 1. **Basic Example of Broadcasting**

- The basic principle of broadcasting is that NumPy can automatically "stretch" smaller arrays to match the dimensions of larger arrays.

Example:

```python
a = np.tile(np.arange(0, 40, 10), (3, 1))  # Create a 2D array by repeating values
print(a)
# Output:
[[ 0 10 20 30]
 [ 0 10 20 30]
 [ 0 10 20 30]]

a = a.T  # Transpose the array
print(a)
# Output:
[[ 0  0  0]
 [10 10 10]
 [20 20 20]
 [30 30 30]]

b = np.array([0, 1, 2])  # 1D array
print(b)
# Output: array([0, 1, 2])

a + b  # Broadcasting the smaller array b across the larger array a
# Output:
array([[ 0,  1,  2],
       [10, 11, 12],
       [20, 21, 22],
       [30, 31, 32]])
```

#### 2. **Changing the Shape of Arrays**

- To perform broadcasting between arrays, NumPy sometimes requires arrays to have compatible shapes. You can change the shape of an array using slicing or `np.newaxis`.

Example:

```python
a = np.arange(0, 40, 10)
print(a.shape)  # Output: (4,)
print(a)
# Output: array([ 0, 10, 20, 30])

# Add a new axis to convert 1D to 2D
a = a[:, np.newaxis]
print(a.shape)  # Output: (4, 1)
print(a)
# Output: 
# [[ 0]
#  [10]
#  [20]
#  [30]]
```

#### 3. **Performing Broadcasting**

- Once you have reshaped the arrays to compatible dimensions, broadcasting can take place. In this case, the 2D array `a` (shape `(4, 1)`) can be broadcasted with the 1D array `b` (shape `(3,)`).

Example:

```python
a + b  # Broadcasting occurs here, the result is:
# Output:
array([[ 0,  1,  2],
       [10, 11, 12],
       [20, 21, 22],
       [30, 31, 32]])
```

The smaller array `b` is stretched along the second axis to match the shape of `a`.

#### **Key Concept:**

- Broadcasting allows arrays of different shapes to be used together in operations. The smaller array is automatically "broadcasted" to match the shape of the larger array. Broadcasting occurs when the following conditions are met:
    - The dimensions of the arrays should be compatible (either the size of a dimension is 1 or the dimensions must be the same).
    - Broadcasting happens from the last dimension to the first dimension, and smaller dimensions are stretched if needed.


# References