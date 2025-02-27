
| Excercise                 | prev. lecture                                         | next lecture                                                    |
| ------------------------- | ----------------------------------------------------- | --------------------------------------------------------------- |
| [[ML AI Modul5 Exercise]] | [[MachineLearning AI Modul 4\| Power Class. alg p.2]] | [[MachineLearning AI Modul 6\|Data preprocess. and hyperparam]] |

# [[Unsupervised Learning]]
![[MachineLearning AI Modul 5.png]]
![[MachineLearning AI Modul 5-1.png]]

# [[clustering]]

## [[K-means Clustering]]
### Using elbow method to find the optimal number of clusters
- In order to evaluate the performance of a [[Supervised Learning]], we do **hyper parameter tuning**
- Thus, to quantify the quality of clustering, we need to use intrinsic metrics -*such as **SSE (distortion)** that we discussed earlier*- to compare the performance of different k-means clustering.
- Based on the **SSE**, we can use graphical tool, so called elbow method, to estimate the optimal number of clusters "k" for a given task.
- Intuitively, we can say that, if **k increases, the distortion will decrease.** This is because the samples will be closer to the centroids they are assigned to.
- The idea behind the elbow method is to identify the value of where the distortion begins to increase most rapidly.
## [[Hierarchical Clustering]]
## [[DBSCAN]]: Density-based spatial clustering of applications with noise
