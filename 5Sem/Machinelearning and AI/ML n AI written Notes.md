## Fitting
- **Overfitting:** Model is too complex, so it doesn't generalize
	- **solution:** More data,
		-  maybe fewer iterations(?)
		- reduce weights
		- [[regularization]]
- **Underfitting:** Too little data(?) Model is too simple, so doesnt learn everything about the data.
	- training below validation
![[ML n AI written Notes.png]]
# Modul 1


# Modul 2

## Preprocessing
- Split into training and test sets
- Reduce or remove useless features
	- saves space, memory and time(?)
- **Reduces columns**
### Feature Selection
ssss
- **Reduces columns**

### Feature Extraction
- combine features
	- New feature! $f_1+f_2=f_3$ 

### Dimensional Reduction
- If we remove / combine features, then the matrix will change dimensions


> [!NOTE] **Ways of reducing dimensions**
> - **Row reduction:** Sampling
> - **Column reduction:** Feature selection, Feature extraction

### Sampling
- Play around with data points
- Take samples of the data (yknow, 'stikprøver') Dont necessarily need all points in a dataset
- **Reduces rows**

## Training ML algorithm for Classification
### Perceptron for classification
- Single layer, singler neuron
#### Decision Function
##### weighted data
- **take weighted data** 
	- Weight-zero to get $\theta$ and do bullshit --weighted sum--
	- (Linear combination of certain input values **X** and wieght vector $\bar{w}$ where **Z**:)
		- $Z=\bar{w_{0}}\bar{x_{0}}+\dots+\bar{w_{n}}\bar{x_{n}}=\bar{w}^{T}\bar{x}$
			- Why transpose? because of how you work with vectors
		- If $Z>\theta,out=1$ else $out=-1$ 
###### Deciding Weights / weighing parameter 
- Two primary choices (in this context):
	- Stepfunction: (bcuz discrete?)
	- Weighted sum: diff. importance, weigh signals then sum
- **If model erros, we have to update weights**
	- $k=0$
	- $k=k+1$
	- $(w_{k} \to \hat{y}_{k})\text{ and then wrap around again}$ maybe idk.
	- $w_{j}=w_{j}+\Delta{w_{j}}$
	- $\Delta{w_{j}}=\eta(y^{()}-y^{()})x_{j}^{()}$
	- **We want to seperate \---------linearly**
		- Classification needs clear boundary since it is --------

### Adaline for classification
- Is much the same as using perceptron, but also uses **Activation function**
- Step function is 0 or 1, but this is linear
	- (You can differentiate that shit)
- ***For Adaline, we can define cost function $J$ to learn weights as sum of Squared Errors (SSE)*** between calculated output and true class labels
### Adaline VS Perceptron
- **When you update feature J:**
	- Adaline uses all data
	- Find local/global min/max ... but cost function = find min
	- convex function -> do diff
### Learning rate <--> Step size
- We don't want to overshoot the minimum, but we also dont want to spend an eternity inching towards it. **therefore, our ethos is:**
	- ssss
- The dream is: **find it fast, but also precisely**
- Dont overshoot the mean
- Difference is how we update weight and learning rate

### Why do we need Feature Scaling?

> [!NOTE] Why do we need Feature Scaling?
> Say we have 2 features, and their range of values are too different. This could introduce problems in our training, in the form of:
> - Bias from the high ranges (ie unnecessarily placing importance on values because of their skewed values)
> 
> This can be removed by having all data use the same scale. **So, we scale data by:**
> - **Standardization**(z-score normalization) 
> 	- (remember standard distributions)
> 	- mean = 0 & std.dev. = 1
> - **Normalization**(min-max normalization/scaling)
> 	- Simple normalize all data to scale from 0..1
> 	- (*1 being the highest value of that feature and 0 being the lowest...**i think***)
> 
> **BUT WHICH IS BETTER?** idk. find out


# Modul 3

==**SKIPPED**== 
# Modul 4
## Fucking trees and Impurities

> [!NOTE] When to stop splitting nodes in a tree?
> - The node is pure (i.e. *100% one type*)
> - When split will exceed max depth
> - improvements in **Purity Score** aren't enough (i.e. *its below an arbitrary threshold*)
> - When the number of examples is below a threshold (*also arbitrary*)


> [!tip] Feature is discrete but non-binary
> Do some cheeky plays with dummy variables and (something hot-encoding).
> **think of it like logic gates and diagrams:**
> 
> **EXAMPLE:** 
> *Ear-type: fluffy, pointy or oval*
> |        -------       |   x  |  y  |
> | ------- | - | - |
> |  Pointy   |   0  |  0  |
> |   -Fluffy   |  0  |  1  |
> |    --Oval    |   1  |  0  |
> 
> **replacing that feature with features x and y can be used to describe those three values and even an extra**





### Impurities 
We want to maximize **Information Gain (IG)**
> [!NOTE] Types of **Impurities**
> - Entropy
> - Gini
> - Classification Error
> 
> **Which to use? Which is best**
> Depends on the depth of the decision tree and ALSO, which is best depends largely on the dataset its used on.

### Random Forest
**Improves on decision trees.** Random forests are also called tree-ensembles

> [!NOTE] **How-to:** Random Forest
> - Construct **bootstrap** data set of size $n$
> 	- randomly choose $n$ samples from the training dataset, **with replacement**
> - At each node randomly choose feature **without replacement**
> - Split node using feature giving the best split for our **objective function**


> [!example] **Out-of-bag dataset** and **Bootstrap dataset**
> - **Bootstrap dataset:** ssss
> - **Out-of-bag dataset:** Parts of the (*original*) dataset, not in the bootstrap set

### **KNN:** k-nearest neighbors
choose $k$(# of neighbors to use) and distance. **Majority vote** decides the label (*decision depending on distance...?*)
**Doesn't learn discriminatory function but memorizes training dataset instead**

# Modul 5
==**SKIPPED**==
# Modul 6
==**SKIPPED**==
# Modul 7
## Multi-layer Artificial Neural Networks
### **MLP:** Multilayer Perceptron



### Activating the neural net via **forward propagation**
- **step 1:** forward the patterns of the training data through the net to generate an putput
- **step 2:** Based on the output we calculate the error that we want to minimize using the cost function (--------)
- **step 3:** Back propagate the error, find its derivative with respect to each weight in the network and update model.

> [!NOTE] a quick aside regarding -----**idk which one of these above**----
> **Good for Computer Vision:** (Do convolutional deep neural network)
> Because an image is a matrix of pixels(which, themselves are vectors) **that is a lot of data to do calculation on...**
> 
> 
> **PURPOSE SEEMS TO BE:** Large & complex dataset with many features. Hard to do manual.

### P
## [[Backpropagation Algorithm]]



# Modul 8


# Modul 9


# Modul 10