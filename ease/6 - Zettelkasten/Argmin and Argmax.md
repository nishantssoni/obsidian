2025-01-25 13:21

Status:

Tags:[[maths]]

# Argmin and Argmax


The **argmin** and **argmax** functions return the input value(s) where a given function achieves its minimum or maximum.

## Definitions
- **Argmin**:
$$
\text{argmin}_x \, f(x) = \{x \mid f(x) \text{ is minimized}\}
$$

- **Argmax**:
$$
\text{argmax}_x \, f(x) = \{x \mid f(x) \text{ is maximized}\}
$$

## Examples
1. If $f(x) = (x - 2)^2$, then:
   - $\text{argmin}_x f(x) = 2$

2. If $f(x) = -x^2 + 4x$, then:
   - $\text{argmax}_x f(x) = 2$

> [!note] 
>  - The result of **argmin** or **argmax** is the **input value(s)**, not the actual minimum or maximum value.
>  -  If multiple inputs achieve the same extremum, the result may be a set of values.
>  - Commonly used in optimization and decision-making problems.


# References