2025-01-30 08:53

Status:

Tags: [[regression]]

# Logistic Regression Collinearity of features

- If we assume feature are independent then we can get Feature importance interpretation  from the weight vectors.
- If there is co-linearity means one get from multiplying or adding some constants, then we cannot interpret feature importance from weight vector.
- Two features are collinear if a feature can be expressed as a function of other feature:
	- $feature_{1} = \alpha feature_{2} + \beta$ 

> [!example] 
> Why we cannot use W vector when features are collinear here is example:
> - let suppose out $W^{*} = <1,2,3>$ which has features as $<f_{1},f_{2},f_{3}>$
> - Now let $f_{2} = 1.5f_{1}$ which is a collinear.
> - if we calculate $W^{*T}x_{q} = x_{q_{1}} + 2x_{q_{2}} + 3x_{q_{3}}$ now if we put $f_{2} = 1.5f_{1}$ the new equation become   $W^{*T}x_{q} = 4x_{q_{1}} + 3x_{q_{3}}$ which results a new weight vector $W^{`} = <4,0,3>$
> - so $W^{*}, W^{`}$ results same equation but both interpretation different $W^{`}$ says that feature 2 does not have any importance but $W^{*}$ says feature 2 has some importance.

- Multi collinear feature is a feature that can be expressed as a function of multiple features.
- Weight vectors are impacted by multi collinear features.
- To use Weight vector for interpreting feature importance then we need to remove multi collinear features;
- ==Multi collinear feature can be determined by adding noise to features(perturbation technique):==
	- first we calculate the weight before perturbation $W^{*}$
	- and then we add small noise($\epsilon$) to the $x_{ij}$ values that we can generate from a random variable with mean 0 and very small variance e.g: $N(0,0.01)$ 
	- and we again train and compute weight after perturbation $W^{`}$
	- if $W^{*}$ and $W^{`}$ weights vector varies(after training) **a lot then** the features are multi collinear.
	- then, we cannot use W vector for feature importance.
	- if they differ slightly then it is okay to continue.
- ==Multi collinear test is mandatory. otherwise you can come in a strange conclusion==
- if you can't use perturbation test then you can always use forward feature selection technique it works for all the algorithms.



# References
[[Logistic Regression Feature importance and model interpretability]]
[[Perturbation Technique]]
[[Classification algorithms Feature importance & Forward Feature Selection]]