
### Under [[Dimension reduction]]
# Overview

## Principal Component Analysis (PCA)
**For unsupervised data compression**
### Bullshit
1. tandardize the d-dimensional dataset
2. Construct the covariance matrix
3. Decompose the covariance matrix into its eigenvectors and eigenvalues
4. Sort the eigenvalues by decreasing order to rank the corresponding eigenvectors
5. Select N eigenvectors which correspond to the N largest eigenvalues, where N is the dimensionality of the new feature space (k < d)
6. Construct a projection matrix w from the "top" N eigenvectors
![[image_Feature Extraction.png]]
## Linear Discriminant Analysis (LDA)
**As a supervised dimensionality reduction technique for maximizing class reparability**
### Bullshit
1. Standardize the d-dimensional dataset (d is the number of features)
2. For each class, compute the d-dimensional mean vector
3. Construct the between-class scatter matrix $S_{B}$ and the within-class scatter matrix $S_{W}$
4. Compute the eigenvectors and corresponding eigenvalues of the matrix $S_{W}^{-1}S_{B}$
5. Sort the eigenvalues by decreasing order to rank the corresponding eigenvectors
6. Choose the N eigenvectors that correspond to the N largest eigenvalues to construct a d k x -dimensional transformation matrix W; the eigenvectors are the columns of this matrix
![[MachineLearning AI Modul 6-8.png]]
## ASDASDASD

> [!NOTE] Title
> **It is not possible to express all PCs in 2D plot**
> However, principle components are ranked:
>  	**PC1 > PC2 > PC3 > PC4 > PC5**
>  	
> 1. S 
>    ![[MachineLearning AI Modul 6-4.png]]
> 2. **Principal Component Analysis**
> 3. S
>     ![[MachineLearning AI Modul 6-5.png]]

> [!IMPORTANT] Title
> Ideally, **we want to get around 90%** variance with **just 2 to 3 PCs so that enough information is retained** while we can still visualize our data on a plot.
> 
> ![[MachineLearning AI Modul 6-6.png]]

s
## Total and explained variance
$$\frac{\lambda_{j}}{\sum_{j=1}^{d}\lambda_{j}}$$
$\lambda_{j}$ -- eigenvalue
![[MachineLearning AI Modul 6-7.png]]
