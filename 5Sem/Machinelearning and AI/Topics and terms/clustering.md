![[clustering.png]]


# ASDASDASD
## Hard vs Soft Clustering
- **Hard clustering** describes a family of algorithms where each sample in a dataset is assigned to exactly one cluster, as in k-means algorithm
- in contras, algorithms for **soft clustering (*fuzzy clustering*)** assign a sample to one or more clusters. A popular example of soft clustering is the **fuzzy C-means (FCM)** algorithm (also called **soft k-means** or **fuzzy k-means**)
	- ==IT HAS HIGH FLEXIBILITY IN APPLICATIONS:==
		- In **image processing,** a pixel might belong to multiple categories (e.g., a boundary pixel could belong partially to two regions).
		- in **topic modeling** or **text clustering**, a document may be associated with multiple topics.
		- in **biological data**, genes or proteins may belong to multiple functional categories or pathways.

## Sub-categories
### [[K-means Clustering]]
#### Elbow Method
**used to find the optimal number of clusters**
- In order to evaluate the performance of a [[Supervised Learning]], we do **hyper parameter tuning**
- Thus, to quantify the quality of clustering, we need to use intrinsic metrics -*such as **SSE (distortion)** that we discussed earlier*- to compare the performance of different k-means clustering.
- Based on the **SSE**, we can use graphical tool, so called elbow method, to estimate the optimal number of clusters "k" for a given task.
- Intuitively, we can say that, if **k increases, the distortion will decrease.** This is because the samples will be closer to the centroids they are assigned to.
- The idea behind the elbow method is to identify the value of where the distortion begins to increase most rapidly.
### [[Hierarchical Clustering]]

### [[DBSCAN]]

### Soft Clustering
##### **Step 1:** Given the data points based on the number of clusters required initialize the membership table with random values
Suppose the given datapoints are {(1,3),(2,5),(6,8)(7,9)}

| Cluster | (1,3) | (2,5) | (4,8) | (7,9) |
| ------- | ----- | ----- | ----- | ----- |
| 1       | 0.8   | 0.7   | 0.2   | 0.1   |
| 2       | 0.2   | 0.3   | 0.8   | 0.9   |
##### **Step 2:** Find out the centroid
![[K-means Clustering-9.png]]
![[Pasted image 20241027192119.png]]

##### **Step 3:** Find out the distance of each point from centroid.
![[K-means Clustering-10.png]]

##### **Step 4:** Update the membership values.
![[K-means Clustering-11.png]]

##### **Step 5:** Repeat the steps (2-4) until the constant values are obtained for hte membership values or difference is less than the tolerance value