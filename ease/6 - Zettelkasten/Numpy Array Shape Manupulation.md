2025-01-22 22:27

Status:

Tags:[[numpy]] [[data_types]] 

# Numpy Array Shape Manupulation


## Flattening

- **Flattening a 2D array into a 1D array**:
    
    ```python
    a = np.array([[1, 2, 3], [4, 5, 6]])
    a.ravel()
    # Output: array([1, 2, 3, 4, 5, 6])
    ```
    
- **Transpose**:
    
    ```python
    a.T
    # Output: 
    # array([[1, 4],
    #        [2, 5],
    #        [3, 6]])
    ```
    
- **Transpose followed by flattening**:
    
    ```python
    a.T.ravel()
    # Output: array([1, 4, 2, 5, 3, 6])
    ```
    

---

## Reshaping

- **Inverse of flattening**:
    
    ```python
    print(a.shape)  # Output: (2, 3)
    print(a)        # Output: [[1, 2, 3], [4, 5, 6]]
    ```
    
- **Flattened array and reshape back**:
    
    ```python
    b = a.ravel()
    print(b)  # Output: [1 2 3 4 5 6]
    b = b.reshape((2, 3))
    print(b)
    # Output: 
    # array([[1, 2, 3],
    #        [4, 5, 6]])
    ```
    
- **Reshape affects the original array if values are changed**:
    
    ```python
    b[0, 0] = 100
    print(a)
    # Output: 
    # array([[100,   2,   3],
    #        [  4,   5,   6]])
    ```
    
- **Reshape may return a copy**:
    
    ```python
    a = np.zeros((3, 2))
    b = a.T.reshape(3 * 2)
    b[0] = 50
    print(a)
    # Output: 
    # array([[0., 0.],
    #        [0., 0.],
    #        [0., 0.]])
    ```
    

---

## Adding a Dimension

- **Using `np.newaxis`**:
    
    ```python
    z = np.array([1, 2, 3])
    z[:, np.newaxis]
    # Output: 
    # array([[1],
    #        [2],
    #        [3]])
    ```
    

---

## Dimension Shuffling

- **Shuffling and accessing specific elements**:
    
    ```python
    a = np.arange(4 * 3 * 2).reshape(4, 3, 2)
    print(a.shape)  # Output: (4, 3, 2)
    print(a[0, 2, 1])  # Output: 5
    ```
    

---

## Resizing

- **Resize array**:
    
    ```python
    a = np.arange(4)
    a.resize((8,))
    print(a)
    # Output: array([0, 1, 2, 3, 0, 0, 0, 0])
    ```
    
- **Restriction on resizing when referenced**:
    
    ```python
    b = a
    a.resize((4,))
    # Error: ValueError: cannot resize an array that references or is referenced.
    ```
    

---

## Sorting Data

- **Sorting along an axis**:
    
    ```python
    a = np.array([[5, 4, 6], [2, 3, 2]])
    b = np.sort(a, axis=1)
    print(b)
    # Output: 
    # array([[4, 5, 6],
    #        [2, 2, 3]])
    ```
    
- **In-place sort**:
    
    ```python
    a.sort(axis=1)
    print(a)
    # Output: 
    # array([[4, 5, 6],
    #        [2, 2, 3]])
    ```
    
- **Fancy indexing with sorting**:
    
    ```python
    a = np.array([4, 3, 1, 2])
    j = np.argsort(a)
    print(j)  # Output: array([2, 3, 1, 0])
    print(a[j])  # Output: array([1, 2, 3, 4])
    ```

# References
[[Numpy Broadcasting]]
