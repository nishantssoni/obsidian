2025-02-11 12:02

Status:

Tags:

# SGD algorithm Intro

Linear regression:
Gradient descent update:
$$
W_{j+1} = W_{j} - r_{s} * \sum ^{n}_{i=1}(-2x_{i})(y_{i} - W_{j}^{T}x_{i})
$$
we change n number of points to k. where $1 \leq k \leq n$

$$
W_{j+1} = W_{j} - r_{s} * \sum ^{k}_{i=1}(-2x_{i})(y_{i} - W_{j}^{T}x_{i})
$$


- Changed iteration over n to k where we compute for k random points.
- As we pick k random points we call this Gradient Descent as Stochastic Gradient Descent.
- As k reduces from n to 1 the number of iterations required to reach optimum increases.
- At each iteration we have k and r changing.
- ==k is randomly picked points between 1 and n which is called as batch size.==
- **r is reduced at each iteration progressively.**

> [!info] 
> when k = 1 it is called SGD, and when k > 1 it is called Batch SGD.
# References