## Hierarchical clustering
- **Two main hierarchical clustering:**
	- **==Agglomerative clustering==**, which has two standard clustering methods(?)
		- *single linkage*
		- *complete linkage*
	- **==Divisive clustering==**

#### Agglomerative clustering
- **==Agglomerative clustering==** *single linkage*
	- We compute the **distances between the most similar members of each pair of clusters** and **merge the two clusters for which the distance between the most similar members is the smallest.**
- **==Agglomerative clustering==** *complete linkage*
	- Is similar to the single linkage but, instead of comparing the most similar members in each pair of clusters, we compare **the most dissimilar members to perform the merge.**
![[MachineLearning AI Modul 5-2.png]]

> [!NOTE] **Agglomerative clustering**
>  **idea:** Ensure nearby points end up in the same cluster
>  
> - start with a collection of $C$ to $n$ singleton clusters
> 	- each cluster contains one data point: $c_{i}-\{x_{i}\}$
> - Repeat until only one cluster is left:
> 	- Find a pair of clusters that is closest: $min_{(i,j)}D(c_{i},c_{j})$
> 	- merge the clusters $c_{i}$, $c_{j}$ into a new cluster $c_{i+j}$
> 	- remove $c_{i}$, $c_{j}$ from the collection $C$, add $c_{i+j}$
> - Produces a dendrogram: hierarchical tree of clusters
> - need to define a distance metric over clusters
> 
> 

##### Example
![[MachineLearning AI Modul 5-3.png]]
![[MachineLearning AI Modul 5-4.png]]
![[MachineLearning AI Modul 5-6.png]]![[MachineLearning AI Modul 5-7.png]]
