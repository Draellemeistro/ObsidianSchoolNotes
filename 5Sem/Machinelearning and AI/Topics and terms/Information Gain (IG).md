## Maximizing information gain - getting the most bang for your buck

In order to split the nodes at the most informative features, we need to define an objective function that we want to optimize via the tree learning algorithm. Here, our objective function is to maximize the information gain at each split, which we define as follows:
$$IG(D_{p},f)=I(D_{p})-\sum_{j=1}^{m}\frac{{N_{j}}}{N_{p}}I(D_{j})$$
where:
- $f$ is the feature to perform the split
- $D_{p}$ and $D_{j}$ are the dataset of the parent and $j$th child node, 
- $I$ is our **_impurity_** measure
- $N_{p}$ is the total number of samples at the parent node
- $N_{j}$ is the number of samples in the $j$th child nide
as we can see the information gain is simply the difference between the impurity of the parent node and the sum of the child node impurities - **the lower the impurity of the child nodes, the larger the information gain.** 

For simplicity and to reduce the combinatorial search space, most libraries implement binary decision trees. This means that each parent node is split into two child nodes, $D_{left}$ and $D_{right}$:
$$IG(D_{p},f)=I(D_{p})-\frac{N_{left}}{N_{p}}I(D_{left})-\frac{N_{right}}{N_{p}}I(D_{right})$$
Now, the three impurity measures or splitting criteria that are commonly used in binary decision trees are:
- **Gini impurity ($I_{G}$)** 
	- can be understood as a criterion to minimize the probability of misclassification.
- **Entropy ($I_{H}$)**
- **classification error ($I_{E}$)** 

> [!NOTE] **Entropy** Definition
> For all **non-empty classes** $(p(i|t)\neq 0)$:
> $$I_{H}(t)=-\sum_{i=1}^{c}p(i|t)\log_{2}p(i|t)$$
> - $p(i|t)$ is the proportion of the samples that belong to class $c$ for a particular node $t$. 
> 
> **the entropy is therefore 0 if all samples at a node belong to the same class, and the entropy is maximal if we have a uniform class distribution**

For example, in a binary class setting the entropy is 0 if $p(i=1|t)=1$ or $p(i=0|t)=0$. If the classes are distributed uniformly with $p(i=1|t)=0.5$ and $p(i=0|t)=0.5$, the entropy is 1. Therefore, we can say that the entropy criterion attempts to maximize the mutual information in the tree.

Intuitively, the **Gini Impurity** can be understood as a criterion to minimize the probability of misclassification.

> [!NOTE] Gini impurity
> can be understood as a criterion to minimize the probability of misclassification:
> $$I_{G}(t)=-\sum_{i=1}^{c}p(i|t)(1-p(i|t))=1-\sum_{i=1}^{c}{p(i|t)}^2$$
> Similar to **entropy**, the **Gini impurity** is maximal if the classes are perfectly mixed, for example, in a binary class setting $(c=2)$:
> $$I_{G}(t)1-\sum_{i=1}^{c}0.5^{2}=2$$
> However, ==in practice both **Gini impurity** and **entropy** typically yield very similar results, and it is often not worth spending much time on evaluating trees using different impurity criteria rather than experimenting with different pruning cut-offs.==


> [!NOTE] Classification error
> $$I_{E}=1-\text{max}\{p(i|t)\}$$
> **Useful criterion for pruning but not recommended for growing a decision tree**, since it is less sensitive to changes in the class probabilities of the nodes. 
> 
> We can illustrate this by looking at the two possible splitting scenarios shown in the following figure:
> 
> ![[Pasted image 20240930085325.png]]


![[Pasted image 20240930085418.png]]
![[Pasted image 20240930085431.png]]
![[Pasted image 20240930085446.png]]

```python
import matplotlib.pylot as plt
import numpy as np
def gini(p):
	return (p) * (1 - (p)) + (1 - p) * (1 - (1-p))
def entropy(p):
	return - p*np.log2(p) - (1 - p)*np.log2((1 - p))
def error(p):
	return 1 - np.max([p, 1 - p])
x = np.arrange(0.0, 1.0, 0.01)
ent = [entropy(p) if p != 0 else None for p in x]
sc_ent = [e*0.5 if e else None for e in ent]
err = [error(i) for i in x]
fig = plt.figure()
ax = plt.subplot(111)
for i, lab, ls, c, in zip([ent, sc_ent, gini(x), err],
						 ['Entropy', 'Entropy (scaled)',
						 'Gini Impurity',
						 'Misclassification Error'],
						 ['-', '-', '--', '-.'],
						 ['black', 'lightgray',
						 'red', 'green', 'cyan']):
	line = ax.plot(x, i, label=lab,
					linestyle=ls, lw=2, color=c)
ax.legend(loc='upper center', bbox_to_anchor=(0.5, 1.15),
		 ncol=5, fancybox=True, shadow=False)
ax.axhline(y=0.5, linewidth=1, color='k', linestyle='--')
ax.axhline(y=1.0, linewidth=1, color='k', linestyle='--')
plt.ylim([0, 1.1])
plt.xlabel('p(i=1)')
plt.ylabel('Impurity Index')
plt.show
```
![[Pasted image 20240930090703.png]]

