2025-01-23 13:47

Status:

Tags:[[matplotlib]] [[graph]]

# Matplotlib Multiple figures


1. **First Figure (Figure 1)**:
    ![[Pasted image 20250123134747.png]]
    - Two subplots:
        - The first subplot shows an exponential decay with oscillations (`f(t)`).
        - The second subplot displays a cosine wave.
2. **Second Figure (Figure 1 again)**:
    ![[Pasted image 20250123134757.png]]
    - Two subplots:
        - The first subplot plots `[1, 2, 3]`.
        - The second subplot plots `[4, 5, 6]`.
3. **Third Figure (Figure 2)**:
    ![[Pasted image 20250123134806.png]]
    - A single plot with `[4, 5, 6]`.

The title of the first subplot in Figure 1 was updated using the new method: `ax1.title.set_text("Easy as 123")`. Let me know if you'd like further assistance!

### Code

```python
import numpy as np
import matplotlib.pyplot as plt

# Define the function
def f(t):
    return np.exp(-t) * np.cos(2 * np.pi * t)

# Create time intervals
t1 = np.arange(0.0, 5.0, 0.1)
t2 = np.arange(0.0, 5.0, 0.02)

# --- First Figure ---
plt.figure(1)

# Subplot 1 in Figure 1
ax1 = plt.subplot(211)  # 2 rows, 1 column, first subplot
ax1.grid()
ax1.plot(t1, f(t1), 'b-')  # Blue line plot
ax1.title.set_text("Exponential Decay with Cosine")

# Subplot 2 in Figure 1
ax2 = plt.subplot(212)  # 2 rows, 1 column, second subplot
ax2.plot(t2, np.cos(2 * np.pi * t2), 'r--')  # Red dashed line
ax2.title.set_text("Cosine Wave")

plt.show()

# --- Second Figure ---
plt.figure(2)

# Subplot 1 in Figure 2
ax1 = plt.subplot(211)  # 2 rows, 1 column, first subplot
ax1.plot([1, 2, 3], 'g-')  # Green line plot
ax1.title.set_text("Simple Line 1")

# Subplot 2 in Figure 2
ax2 = plt.subplot(212)  # 2 rows, 1 column, second subplot
ax2.plot([4, 5, 6], 'm-')  # Magenta line plot
ax2.title.set_text("Simple Line 2")

plt.show()

# --- Third Figure ---
plt.figure(3)

# Default single subplot in Figure 3
plt.plot([4, 5, 6], 'k--')  # Black dashed line plot
plt.title("Default Subplot in Third Figure")
plt.grid()

plt.show()
```

---

### Output

1. **Figure 1**:
    
    - **Subplot 1**: Blue exponential decay with cosine.
    - **Subplot 2**: Red dashed cosine wave.
2. **Figure 2**:
    
    - **Subplot 1**: Green line `[1, 2, 3]`.
    - **Subplot 2**: Magenta line `[4, 5, 6]`.
3. **Figure 3**:
    
    - Single plot with a black dashed line `[4, 5, 6]`.

Each figure has its own plots and styling for better visualization!
# References