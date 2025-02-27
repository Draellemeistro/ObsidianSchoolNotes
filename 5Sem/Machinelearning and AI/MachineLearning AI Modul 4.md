| Excercise                                   | prev. lecture                                            | next lecture                                          |
| ------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------- |
| [[ML AI Modul4 Exercise\|MLAI Excercise 4]] | [[MachineLearning AI Modul 3\|Powerful Class. algs p.1]] | [[MachineLearning AI Modul 5\|Unsupervised Learning]] |

# Powerful Machine Learning Algorithms for Classification p.2
## What we learn:
- [[Decision tree classifiers]]
	- [[Information Gain (IG)]]
- [[k-nearest neighbor (KNN)]]
- [[majority vote]]


> [!question] **Summary from book**
> - Decision trees are attractive if we care about interpretability.
> - [[logistic regression]] is not only a useful model for online learning via stochastic gradient descent but also allows us to predict the probability of a particular event.
> - Although support vector machines are powerful linear models that canb be extended to nonlinear problems via the kernel trick, they have many parameters that have to be tuned in order to make good predictions.
> 	- in contrast, ensemble methods such as random forest don't require much parameter tuning and don't overfit as easily as decision trees, which makes the attractive models for many practical problem domains.
> 	- [[k-nearest neighbor (KNN)]] offers alternative approach to classification via lazy learning that allows us to make predictions without any model training, but more computationally expensive prediction step.
> 
> **However, no algorithm will be able to make good predictions without informative and discriminatory features**

# Decision tree learning

> [!NOTE] **[[Decision tree classifiers]]**
> **attractive models if we care about interpretability**
> Think of this model as breaking down our data by making decision based on asking a series of questions.
> 
> Using the decision algorithm. we start at the tree root and split the data on the feature that results in the largest **[[Information Gain (IG)]]**. In an iterative process, we can then repeat this splitting procedure at each child node until the leaves are pure.
> 
> ==can result in a very deep tree with many nodes, which can easily lead to overfitting==
> 

# K-nearest  neighbors - a lazy learning algorithm


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

ss


> [!tip] **Parametric versus nonparametric models**
> Machine learning algorithms can be grouped into **parametric** and **nonparametric** models.
> ![[Pasted image 20240930092115.png]]


![[Pasted image 20240930092353.png]]