2025-01-19 00:08

Status:

Tags:[[numpy]] 

# Numpy Numerical and Logical Operations


### Numerical Operations in NumPy

NumPy provides various ways to perform elementwise operations, matrix multiplications, logical operations, transcendental functions, and reductions efficiently.

#### 1. **Elementwise Operations with Scalars**

- NumPy operations like addition, subtraction, multiplication, and power are applied elementwise to arrays.

Example:

```python
a = np.array([1, 2, 3, 4])
print(a + 1)  # Output: [2, 3, 4, 5]
print(a ** 2)  # Output: [1, 4, 9, 16]
```

- Elementwise operations with another array:

```python
b = np.ones(4) + 1
print(a - b)  # Output: [-1.  0.  1.  2.]
print(a * b)  # Output: [ 2.  4.  6.  8.]
```

- **Matrix Multiplication:**
- Simple elementwise multiplication:
    
    ```python
    c = np.array([[1, 2], [3, 4]])
    d = np.array([[5, 6], [7, 8]])
    print(c * d)  # Output: [[ 5 12] [21 32]]
    ```
    
- **Matrix dot product:**
    
    ```python
    print(c.dot(d))  # Output: [[19 22] [43 50]]
    ```
    

#### 2. **Comparisons**

- **Elementwise Comparisons:**
    
    ```python
    a = np.array([1, 2, 3, 4])
    b = np.array([5, 2, 2, 4])
    print(a == b)  # Output: [False, True, False, True]
    print(a > b)   # Output: [False, False, True, False]
    ```
    
- **Array-Wise Comparisons:**
    
    ```python
    c = np.array([1, 2, 3, 4])
    print(np.array_equal(a, b))  # Output: False
    print(np.array_equal(a, c))  # Output: True
    ```
    

#### 3. **Logical Operations**

- Logical operations like `or` and `and` work elementwise on boolean arrays.
    
    ```python
    a = np.array([1, 1, 0, 0], dtype=bool)
    b = np.array([1, 0, 1, 0], dtype=bool)
    print(np.logical_or(a, b))  # Output: [ True  True  True False]
    print(np.logical_and(a, b)) # Output: [ True False False False]
    ```
    

#### 4. **Transcendental Functions**

- NumPy provides various mathematical functions for trigonometric, logarithmic, and exponential operations.

Example:

```python
a = np.arange(5)
print(np.sin(a))  # Output: [ 0.          0.84147098  0.90929743  0.14112001 -0.7568025 ]
print(np.log(a))  # Output: [ -inf   0.    0.693 1.098 1.386]
print(np.exp(a))  # Output: [  1.          2.71828183  7.3890561  20.08553692  54.59815003]
```

#### 5. **Shape Mismatch**

- Operations on arrays with mismatched shapes result in an error.

```python
a = np.arange(4)
print(a + np.array([1, 2]))  # Error: operands could not be broadcast together
```

#### 6. **Basic Reductions**

- **Sum Operations:**
    
    ```python
    x = np.array([1, 2, 3, 4])
    print(np.sum(x))  # Output: 10
    print(x.sum(axis=0))  # Sum along columns (no change for 1D) - Output: 10
    
    # For 2D arrays
    x = np.array([[1, 1], [2, 2]])
    print(x.sum(axis=0))  # Sum along columns: Output: [3, 3]
    print(x.sum(axis=1))  # Sum along rows: Output: [2, 4]
    ```
    
- **Other Reductions:**
    
    - **Min/Max:**
        
        ```python
        print(x.min())  # Output: 1
        print(x.max())  # Output: 3
        ```
        
    - **Argmin/Argmax (index of min/max):**
        
        ```python
        print(x.argmin())  # Output: 0 (index of the minimum element)
        print(x.argmax())  # Output: 1 (index of the maximum element)
        ```
        

In summary, NumPy's elementwise operations allow easy manipulation of array data. Comparisons and logical operations enable condition-based array manipulations. Transcendental functions make advanced mathematical calculations easy, and reductions provide efficient ways to compute summaries like sums, minimums, and maximums.


### Logical Operations in NumPy

NumPy provides several logical operations for working with boolean arrays. These operations can be applied to individual elements or entire arrays. Below are some key logical operations:

#### 1. **`np.all()`**

- This function checks if **all** elements in the array evaluate to `True`. If any element is `False`, it returns `False`.

Example:

```python
np.all([True, True, False])  # Output: False
```

#### 2. **`np.any()`**

- This function checks if **any** element in the array evaluates to `True`. If at least one element is `True`, it returns `True`.

Example:

```python
np.any([True, False, False])  # Output: True
```

#### 3. **Array Comparisons**

- Logical operations like `np.all()` and `np.any()` can be applied to arrays as well. These allow comparison of arrays for conditions across all or some elements.

Example:

```python
a = np.zeros((50, 50))
np.any(a != 0)  # Output: False (no element is non-zero)
np.all(a == a)  # Output: True (all elements are equal to themselves)
```

#### 4. **Logical AND (&) and OR (|) with Arrays**

- You can combine comparisons using logical AND (`&`) and OR (`|`).
- `&` represents logical AND, and `|` represents logical OR.

Example:

```python
a = np.array([1, 2, 3, 2])
b = np.array([2, 2, 3, 2])
c = np.array([6, 4, 4, 5])
result = ((a <= b) & (b <= c)).all()  # Output: True
```

- Here, the logical condition checks if each element of `a` is less than or equal to the corresponding element in `b` and if each element of `b` is less than or equal to the corresponding element in `c`. The `all()` function ensures that this condition holds true for all elements.

These logical operations are useful for filtering data, validating conditions, and performing elementwise logical tests on arrays.

# References