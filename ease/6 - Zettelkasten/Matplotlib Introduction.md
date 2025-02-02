2025-01-22 22:39

Status:

Tags: [[matplotlib]] [[graph]]

# Introduction to Matplotlib


## Overview

- `matplotlib.pyplot`: A module providing MATLAB-like command-style functions to manipulate figures and plots.
- Functions include creating figures, defining plotting areas, plotting lines, adding labels, and customizing plots.

---

## Basic Plotting

- **Single List (Y-axis values only)**:
    
    ```python
    import matplotlib.pyplot as plt
    
    plt.plot([2, 4, 6, 4])  # Y values; X defaults to indices [0, 1, 2, 3]
    plt.ylabel("Numbers")
    plt.xlabel("Indices")
    plt.title("MyPlot")
    plt.show()
    ```
    ![[Pasted image 20250122224125.png]]
- **Explicit X and Y values**:
    
    ```python
    plt.plot([1, 2, 3, 4], [1, 4, 9, 16])  # X vs Y
    plt.ylabel("Squares")
    plt.xlabel("Numbers")
    plt.grid()  # Enable grid
    plt.show()
    ```
    ![[Pasted image 20250122224147.png]]

---

## Formatting Lines and Markers

- **Customize Plot Style**:
    
    ```python
    plt.plot([1, 2, 3, 4], [1, 4, 9, 16], 'ro')  # Red dots
    plt.grid()
    plt.show()
    ```
    
- **Multiple Line Styles**:
    
    ```python
    import numpy as np
    t = np.arange(0., 5., 0.2)
    
    plt.plot(t, t**2, 'b--', label='^2')    # Blue dashes
    plt.plot(t, t**2.2, 'rs', label='^2.2')  # Red squares
    plt.plot(t, t**2.5, 'g^', label='^2.5')  # Green triangles
    plt.legend()  # Add legend
    plt.grid()
    plt.show()
    ```
    ![[Pasted image 20250122224305.png]]

---

## Controlling Line Properties

- **Set Line Width**:
    
    ```python
    x = [1, 2, 3, 4]
    y = [1, 4, 9, 16]
    plt.plot(x, y, linewidth=5.0)  # Line width
    plt.show()
    ```
    ![[Pasted image 20250122224318.png]]
- **Using `setp` for Properties**:
    
    ```python
    x1 = [1, 2, 3, 4]
    y1 = [1, 4, 9, 16]
    x2 = [1, 2, 3, 4]
    y2 = [2, 4, 6, 8]
    lines = plt.plot(x1, y1, x2, y2)  # Two lines
    
    # Python style
    plt.setp(lines[0], color='r', linewidth=2.0)
    
    # MATLAB style
    plt.setp(lines[1], 'color', 'g', 'linewidth', 2.0)
    plt.grid()
    plt.show()
    ```
![[Pasted image 20250122224334.png]]
# References