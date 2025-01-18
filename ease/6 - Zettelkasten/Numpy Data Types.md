2025-01-18 23:56

Status:

Tags:[[numpy]] [[data_types]]

# Numpy Data Types

### Basic Data Types in NumPy

NumPy arrays support a variety of data types, which determine how the array elements are stored in memory. These data types also influence the operations that can be performed on the arrays.

#### Default Data Types

When creating arrays in NumPy, the default data type is often chosen based on the values provided.

For example, when creating an array with integer values, NumPy uses a default integer type (`int64` on 64-bit systems).

```python
a = np.arange(10)
print(a.dtype)  # Output: dtype('int64')
```

#### Explicit Data Type Specification

You can explicitly specify the data type when creating an array using the `dtype` argument. For example, specifying a floating-point type (`float64`):

```python
a = np.arange(10, dtype='float64')
print(a)  # Output: [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
```

#### Default Data Type for Zero and One Arrays

The default data type for arrays created using functions like `np.zeros()` is `float64`:

```python
a = np.zeros((3, 3))
print(a)  # Output: [[0. 0. 0.]
          #          [0. 0. 0.]
          #          [0. 0. 0.]]
print(a.dtype)  # Output: dtype('float64')
```

### Other Common Data Types in NumPy

1. **Complex Data Type**: NumPy also supports complex numbers, represented as `complex128`:
    
    ```python
    d = np.array([1+2j, 2+4j])
    print(d.dtype)  # Output: complex128
    ```
    
2. **Boolean Data Type**: Arrays can also hold boolean values (`True` or `False`):
    
    ```python
    b = np.array([True, False, True, False])
    print(b.dtype)  # Output: dtype('bool')
    ```
    
3. **String Data Type**: NumPy supports arrays of strings, with each string stored as a Unicode string (`dtype('<U5')` indicates 5-character Unicode strings):
    
    ```python
    s = np.array(['Ram', 'Shyam', 'Geeta'])
    print(s.dtype)  # Output: dtype('<U5')
    ```
    

### Character Codes for NumPy Data Types

NumPy uses character codes to identify the various data types:

- **'b'** − Boolean
- **'i'** − (signed) integer
- **'u'** − unsigned integer
- **'f'** − floating-point
- **'c'** − complex-floating point
- **'m'** − timedelta
- **'M'** − datetime
- **'O'** − (Python) objects
- **'S', 'a'** − (byte-)string
- **'U'** − Unicode string
- **'V'** − raw data (void)

For more details on these data types, you can refer to the official NumPy documentation on [data types](https://docs.scipy.org/doc/numpy-1.10.1/user/basics.types.html).

# References