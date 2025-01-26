2025-01-25 12:49

Status: #hard

Tags:[[regression]] [[functions]]

# Logistic Regression Mathematic Formulation of Objective Function

- A function is monotonic which increases with x at all values means when x increases g(x) also increases.
- Sigmoid and Log(x) is a monotonic function.
- If a function is monotonic then when applied a monotonic function retains same maxima or minima.
- theorem said that if g(x) is monotonic then $argmin \ f(x) = argmin \ g(f(x))$
	- $let \ x^{*} \ = \ argmin_{x} \ f(x); f(x) = x^{2}$
	- $let \ x^{'} \ argmin \ g(f(x)) \ ; \ g(x) = \log(x) \ then \ g(f(x)) = \log(x^{2})$
	- so we can say minimum of $x^{2}$ is also minimum of $\log(x^{2})$ which x = 0
	- so we can conclude that $x^{*} = x^{'}$
- Now our original optimization problem is as follow:

$$
W^{*}=argmax_{w}\left( \sum_{i=1}^{n} \frac{1}{1+\exp(-y_{i}W^{T}x_{i})} \right)
$$
$$
W^{*}=argmax_{w}\left( \sum_{i=1}^{n} \log( \frac{1}{1+\exp(-y_{i}W^{T}x_{i})}) \right)
$$
$$
W^{*}=argmax_{w}\left( \sum_{i=1}^{n} -\log(1+\exp(-y_{i}W^{T}x_{i}) \right)
$$
			$maximizing \ of \ f(x) \ is \ same \ as \ minimizing -f(x)$
$$
so \ we \ can \ say \ that \ argmax_{x} \ of \  f(x) = argmin_{x} \ of\ -f(x)
$$

$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i}) \right) \ where \ y_{i} = [-1, 1]
$$
$$
the \ above \ is \ the for m ulation \ for \ the \ optimization \ for \ log istic \  regression
$$
Now, is we remove 1 from inside log then the equation become
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(\exp(-y_{i}W^{T}x_{i}) \right)
$$
here, we cancel log and exp the the new formulation become 
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} (-y_{i}W^{T}x_{i}) \right)
$$
$$
W^{*}=argmax_{w}\left( \sum_{i=1}^{n} (y_{i}W^{T}x_{i}) \right)  \ where \ y_{i} = [-1, 1]
$$

The formulation is same but the sigmoid version will be less impacted by outliers.

**Probabilistic interpretation:**
$$
W^{*} = argmin \sum_{i=1}^{n} (-y_{i} \log(p_{i}) - (1-y_{i})\log(1-p_{i}))) \ where \ p_{i} = \sigma(w^{T}x_{i}) \ a nd \ y_{i} = 0,1
$$
**Above Geometric interpretation:**
$$
W^{*}=argmin_{w}\left( \sum_{i=1}^{n} \log(1+\exp(-y_{i}W^{T}x_{i}) \right) \ where \ y_{i} = -1, 1
$$
 
**both interpretation are similar but uses different method to derive geometry methods is easy and also there is loss function interpretation which also stated similar function**
# References
[[Sigmoid Function]]
[[Logistic Regression Sigmoid Function (squashing)]]
[[Monotonic Function]]
[[Argmin and Argmax]]
[[Objective Function]]