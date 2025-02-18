2025-02-17 08:49

Status:

Tags:

# PCA Geometric intuition

![[Pasted image 20250217084955.png]]

- If we want to reduce dimensionalit from 2D to 1D, we can skip feature f1 as the spread across the feature is very less than spread across the feature f2 (because more spread or variance more information).
- Another case: 
	- Let y = x be the underlying relationship between two features and let X be column standardized, and the plot is such that there is sufficient variance on both features. Say, we rotate the axes and reach an orientation were spread on $f_{2}^{'} \ll f_{1}^{'}$  (perpendicular to $f_{2}^{'}$) then we can drop $f_{2}^{'}$.
- So data transformation can also find maximum variance features. This will help us reduce dimensionality.
- Our objective is:
	- We want to find a direction $f_{1}^{'}$ such that the variance of the data points projected onto $f_{1}^{'}$ is maximum and we can skip $f_{2}^{'}$ features with minimum spread.

![[Pasted image 20250217085226.png]]
# References