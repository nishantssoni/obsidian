2025-02-09 06:06

Status:

Tags: [[maths]]

# Optimization problems Vector calculus Grad

- Differentiation of vectors results in a vector.
- we will be applying element wise partial differentiation.

- let $f(x) = y = a^{T}x = \sum ^{d}_{i=1} a_{i}x_{i}$
- where x is vector $x= <x_{1},x_{2},x_{3},\dots x_{n}>$ 
- where a is scalar $a = <a_{1},a_{2}, \dots, a_{n} >$ 

**$\frac{df}{dx}$ is a scalar differentiation but for vector we us $\nabla_{x}f$ called del or grad symbol**

so insted of solving for all we split each element use partial differentiation.
e.g $\frac{\partial f}{\partial x_{1}}$ , $\frac{\partial f}{\partial x_{2}}$ etc.

so, $$
\nabla_{x}f = \left[ \begin{matrix}
\frac{\partial f}{\partial x_{1}}  \\
\frac{\partial f}{\partial x_{2}} \\
\dots \\
\frac{\partial f}{\partial x_{d}}
\end{matrix} \right]
$$
==we can see the resultant is also a vector==



Logistic loss:
$$
f(W)=a\sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i})  + \lambda (||W||^{2})_{2}
$$
Solving the logistic loss is hard and thus we can use gradient descent technique

# References