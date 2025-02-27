# [[clustering]]
## Density-based spatial clustering of applications with noise
- DBSCAN, which does not make assumptions about spherical clusters like [[K-means Clustering]], nor does it partition the dataset into hierarchies that require a manual cut-off point

![[MachineLearning AI Modul 5-8.png]]
- As its name implies, density-based clustering assigns cluster labels based on dense regions of points
- A point is considered **a core point if at least a specified number (MinPts) of neighborung points fall within the specified radius $\epsilon$**.
- A border point is a point that **has fewer neighbors than MinPts within $\epsilon$**, but lies within the $\epsilon$. 
- All other points that are neither core nor border points are considered noise points.

- After labeling the points as core, border, or noise, the DBSCAN algorithm can be summarized in two simple steps:
	- Form a separate cluster for each core point or connected group of core points (core points are connected if they are no farther away than $\epsilon$).
	- Assign each border point to the cluster of its corresponding core point.
![[MachineLearning AI Modul 5-9.png]]

