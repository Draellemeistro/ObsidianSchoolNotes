
# K-means Algorithm
1. Select inputs
2. select k cluster centers
3. assign cases to closest center
	1. We use **Euclidean distance** to calculate the find the closest center
4. update cluster centers
	1. We use **Euclidean distance** to calculate the find the closest center
5. re-assign cases
6. repeat steps 4 and 5 until convergence

#### step 3 from the above list
![[K-means Clustering.png]]
#### step 4 from the above list
![[K-means Clustering-1.png]]
![[K-means Clustering-2.png]]
#### step 5 from the above list
![[K-means Clustering-3.png]]
#### When the algorithm converges
![[K-means Clustering-4.png]]

> [!NOTE] **K-means algorithm**
> Randomly initialize $K$ cluster centroids
> ```C
> # Randomly initialize K cluster centroids #
> Repeat {
> 	# Assign points to cluster centroids
> 	for i = 1 to m
> 		c^(i) := index (from 1 to K) of cluster
> 			centroid closest to x^(i)
> 	# Move cluster centroids
> 	for k = 1 to K
> 		mu_k := average (mean) of points assigned to cluster k
> }
> ```
> ![[K-means Clustering-5.png]]

# K-means Clustering
- When we're applying k-means to real world data using a Euclidea distance metric, we want to make sure that the features are measured on the same sclae and apply **z-score standardization**
- Another drawback of k-means: we have to **specify the number of clusters, k, a priori**. The number of clusters may not be so obvious in real-world application
- There are different types of clustering algorithms, **hierarchical and density-based clustering.** Neither type of algorithm require us to specify **the clusters upfront or assume spherical structures in our dataset.**

- We have discussed the class k-means algorithm that uses a **random seed to place the initial centroids,** which can sometimes result in **bad clustering or slow convergence if the initial centroids are chosen poorly**
	- ==SO, HOW TO SOLVE THIS?==
	- One way to address this is to run the k-means algorithm multiple times on a dataset and choose the best performing model in term of the **[[Sum of Square Error]]**
	- ![[K-means Clustering-6.png]]
	- $$SSE=\sum_{i=1}^{n}\sum_{j=1}^{k}w^{i,j} \|x^{(i)}-\mu^{(j)}\|_{2}^2$$

## K-means++ Clustering
- Another strategy is to place the initial centroids far away from each other vi k-means++ algorithm, which leads to better and more consistent results than the classic k-means algorithm.
#### How does k-means++ clustering work?
###### **Step 1:** Randomly select the first centroid from the data points.
![[K-means Clustering-7.png]]
###### **Step 2:** For each data point compute its distance from the previously chosen centroid.

###### **Step 3:** Select the next centroid from the data points such that the probability of choosing a point as a centroid is directly proportional to its distance from the previously chosen centroid ( i.e. the point having maximum distance from the nearest centroid is most likely to be sleected as next centroid)
![[K-means Clustering-8.png]]

## Hard versus Soft Clustering
- **Hard clustering** describes a family of algorithms where each sample in a dataset is assigned to exactly one cluster, as in k-means algorithm
- in contras, algorithms for **soft clustering (*fuzzy clustering*)** assign a sample to one or more clusters. A popular example of soft clustering is the **fuzzy C-means (FCM)** algorithm (also called **soft k-means** or **fuzzy k-means**)
	- ==IT HAS HIGH FLEXIBILITY IN APPLICATIONS:==
		- In **image processing,** a pixel might belong to multiple categories (e.g., a boundary pixel could belong partially to two regions).
		- in **topic modeling** or **text clustering**, a document may be associated with multiple topics.
		- in **biological data**, genes or proteins may belong to multiple functional categories or pathways.

## Soft clustering
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
