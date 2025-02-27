# [[Types of Data Preprocessing]]

# Dealing with missing data
Samples could be missing one or more values for various reasons.

Most computational tools are unable to handle such missing values, or produce unpredictable result if we simply ignore them
- **Eliminate the samples or features with missing values**
	- ![[MachineLearning AI Modul 6.png]]

**==However, there is a problem when we eliminate rows or columns. What kind of problem? How to solve it?==**
## [[Imputing Missing Values]]

# Handling Categorical Data
> [!NOTE] **Categorical Data:**
> Nominal and Ordinal features, e.g.:
> **Color, Size, Price, classlabel**
> 1. gren, M, 10.1, class1
> 2. red, L, 13.5, class2
> 3. blue, XL, 15.3 class1
> 
> vvv bliver til vvvv
> $XL=L+1=M+2$
> 1. gren, 1, 10.1, class1
> 2. red, 2, 13.5, class2
> 3. blue, 3, 15.3 class1

## [[Encoding]] Class Labels
- Many machine learning librarires require that class labels are encoded as integer values.
- Although most estimators for [[Classification]] in scikit-learn convert class labels to integers internally, it is considered good practice to provide class labels as integer arrays to avoud technical glitches

```python
>>> import numpy as np
>>> class_mapping = {label:idx for idx, label in
...             enumerate (np.unique (df ['classlabel'] ) ) ]

>>> class_mapping
{'class1': 0, 'class2': 1}
```

```python
>>> df ['classlabel'] = df ['classlabel' ] .map (class_mapping)
>>> df
	color  size  price  classlabel
0	green   1    10.1       0
1	red     2    13.5       1
2	blue    3    15.3       0
```

# next