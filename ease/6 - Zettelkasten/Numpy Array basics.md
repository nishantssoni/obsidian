2025-01-18 23:52

Status:

Tags: [[numpy]] [[array]] [[data_structure]]

# Numpy Array basics


### Introduction to NumPy

NumPy is an extension package for Python that provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays. It is widely used for scientific computing due to its efficiency and convenience.

#### Key Features of NumPy:

- **Memory-efficient container** for fast numerical operations.
- Allows for multi-dimensional arrays (1D, 2D, etc.).
- **Closer to hardware** for better performance.
- Ideal for **scientific computation** with high-performance math functions.

### NumPy Array Object

A **NumPy array** is a grid of values, all of the same type, and indexed by a tuple of non-negative integers. These arrays are more efficient than Python lists for large data and allow for fast numerical operations.

#### Basic Examples:

```python
import numpy as np

# 1D array (vector)
a = np.array([0, 1, 2, 3])
print(a)  # Output: [0 1 2 3]

# Using arange to create an array
print(np.arange(10))  # Output: [0 1 2 3 4 5 6 7 8 9]
```

### Why NumPy is Useful:

NumPy provides significant speed improvements over regular Python lists due to its optimized C implementation for numerical operations. The following example shows the time difference between using Python lists and NumPy arrays for squaring numbers:

```python
# Using a list in Python
L = range(1000)
%timeit [i**2 for i in L]  # Time: 180 µs ± 447 ns per loop

# Using NumPy
a = np.arange(1000)
%timeit a**2  # Time: 840 ns ± 5.43 ns per loop
```

### Dimensionality of NumPy Arrays:

- **1D array**: Called a **vector**.
- **2D array**: Called a **matrix**.
- **ND array**: Called a **tensor** (n-dimensional arrays).

#### Example of Array Dimensions:

```python
# 1D array
a = np.array([0, 1, 2, 3])
print(a.ndim)  # Output: 1
print(a.shape)  # Output: (4,)
print(len(a))  # Output: 4

# 2D array
b = np.array([[0, 1, 2], [3, 4, 5]])
print(b.ndim)  # Output: 2
print(b.shape)  # Output: (2, 3)
print(len(b))  # Output: 2

# 3D array
c = np.array([[[0, 1], [2, 3]], [[4, 5], [6, 7]]])
print(c.ndim)  # Output: 3
print(c.shape)  # Output: (2, 2, 2)
```

### Functions for Creating Arrays

1. **Using `arange()` function**: Similar to Python's built-in `range()`, but returns a NumPy array.
    
    ```python
    a = np.arange(10)  # Creates an array [0, 1, 2, ..., 9]
    print(a)
    
    b = np.arange(1, 10, 2)  # Creates an array [1, 3, 5, 7, 9]
    print(b)
    ```
    
2. **Using `linspace()` function**: Creates arrays of evenly spaced values between two numbers.
    
    ```python
    a = np.linspace(0, 1, 6)  # Creates an array of 6 points between 0 and 1
    print(a)
    ```
    
3. **Common Arrays**:
    
    - **Ones Array**:
        
        ```python
        a = np.ones((3, 3))  # Creates a 3x3 array filled with 1s
        print(a)
        ```
        
    - **Zero Array**:
        
        ```python
        b = np.zeros((3, 3))  # Creates a 3x3 array filled with 0s
        print(b)
        ```
        
    - **Identity Matrix**:
        
        ```python
        c = np.eye(3)  # Creates a 3x3 identity matrix
        print(c)
        ```
        
4. **Using `diag()` Function**:
    
    - **Creating a Diagonal Matrix**:
        
        ```python
        a = np.diag([1, 2, 3, 4])  # Creates a diagonal matrix
        print(a)
        ```
        
    - **Extracting Diagonal**:
        
        ```python
        np.diag(a)  # Output: [1, 2, 3, 4]
        ```
        
5. **Random Arrays**:
    
    - **Uniform Random Array**:
        
        ```python
        a = np.random.rand(4)  # Array of 4 random values between 0 and 1
        print(a)
        ```
        
    - **Standard Normal Random Array**:
        
        ```python
        a = np.random.randn(4)  # Samples from a standard normal distribution
        print(a)
        ```
        
    - **Custom Normal Distribution**:
        
        ```python
        a = 2 * np.random.randn(4) + 3  # Samples from N(3, 2^2)
        print(a)
        ```
        


# References
https://numpy.org/doc/
