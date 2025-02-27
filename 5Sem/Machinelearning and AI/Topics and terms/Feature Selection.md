### Under [[Dimension reduction]]


> [!NOTE] **ELI5:** [[Feature Selection]]
> A way to reduce complexity of a model and avoid [[overfitting and underfitting|overfitting]], is [[Dimension reduction]] via **[[Feature Selection]]**, which is especially useful for **unregularized models**
> 
> 

# Overview
## Sequential Backward Selection (SBS)
1. Initialize the algorithm with k=d, where d is the dimensionality of the full feature space $X_{d}$
2. Determine the feature $x^{-}$ that maximizes the criterion: $x^{-} = \text{argmax } J (X_{k}-x))$ where $x \in X_{k}$
3. Remove the feature $x^{-}$ from the feature set: $X_{k-1}=X_{k}-x^{-};k=k-1$
4. Terminate if k equals the number of desired features; otherwise, go to step 2.
	1. ![[MachineLearning AI Modul 6-2.png]]
