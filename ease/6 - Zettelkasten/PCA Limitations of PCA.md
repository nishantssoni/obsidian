2025-02-18 11:04

Status:

Tags:

# PCA Limitations of PCA

- **Loss of information:**
	- cases for hyper-spheres, separable data points on high dimensionality can get crowded at several locations making it inseparable at low Dimensionality.

![[Pasted image 20250218110556.png]]
- ​ First diagram:
	- large percentage of information loss.
- Second diagram:
	- There are visible groups but when we reduce to 1-d then the v2 value will collapse and make us confused for separation so from PCA we can loss nice groups or clusters of data.
- Third diagram:
	- It's a nice sine wave-like curve, if we reduce to 1-D and project all points to V1 then we can lose the nice structure which may help us to separate.

# References
[[KNN Limitations]]