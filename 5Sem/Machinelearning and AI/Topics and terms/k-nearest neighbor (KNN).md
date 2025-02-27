> [!NOTE] [[k-nearest neighbor (KNN)]]
> - Supervised learning algorithm is the **[[k-nearest neighbor (KNN)]] classifier**.
> - Is fundamentally different from the learning algorithms we have discussed thus far.
> - typical example of a **lazy learner** 
> 	- Lazy because it doesn't learn a discriminative function from the training data, but memorizes the training dataset instead.
> 
> Fairly straight forward, summarized by steps:
> 1. Choose the number of **_k_** and a distance metric
> 2. find the k-nearest neighbors of the sample that we want to classify
> 3. Assign the class label by majority vote.
> 
> Following figure illustrates how a new data point (?) is assigned the triangle class label based on majority voting among its five nearest neighbors:
> ![[Pasted image 20240930092328.png]]

![[Pasted image 20240930092344.png]]