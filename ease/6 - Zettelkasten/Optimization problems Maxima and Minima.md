2025-02-09 05:45

Status:

Tags: [[maths]]

# Optimization problems Maxima and Minima

- Maxima: The maximum value a function takes.
- Minima: The minimum value a function takes.
- Slope at maxima / minima / saddle point = 0 = $\frac{df}{dx}$

**example: **
$$f(x) = \log(1 + e^{ax})$$
$$
f^{'}(x) =  \frac{a *e^{ax}}{1 + e^{ax}}
$$

**Most of the functions cannot be readily solved, we will use SGD to solve optimization problems.**

### 📊 Maxima and Minima of a Function

To find the **maxima** and **minima** of a function \( f(x) \), follow these steps:

---

#### ✅ **Step 1: Find the First Derivative**

Calculate the first derivative of the function:

$$
f'(x)
$$

---

#### ✅ **Step 2: Determine Critical Points**

Set the first derivative equal to zero and solve for \( x \):

$$
f'(x) = 0
$$

The solutions are called **critical points**.

---

#### ✅ **Step 3: Apply the Second Derivative Test**

1. Find the second derivative:

$$
f''(x)
$$

2. Evaluate the second derivative at each critical point \( x = c \):

- If \( f''(c) > 0 \), there is a **local minimum** at \( x = c \).
- If \( f''(c) < 0 \), there is a **local maximum** at \( x = c \).
- If \( f''(c) = 0 \), the test is **inconclusive** (check further using other methods).



# References
[[Optimization problems Gradient descent geometric intuition]]