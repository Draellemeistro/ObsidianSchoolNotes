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
> 3. blue, 3, 15.3 class1\

## [[Encoding]] Class Labels
- Many machine learning librarires require that class labels are encoded as integer values.
- Although most estimators for [[Classification]] in scikit-learn convert class labels to integers internally, it is considered good practice to provide class labels as integer arrays to avoud technical glitches
### Python code example
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

## One-hot encoding on nominal features

> [!NOTE] One-hot encoding
> asdddddd

### Python example
```python
>>> X = df [ ['color', 'size', 'price'] ]. values
>>> color_le = LabelEncoder ()
>>> X[:, 0] = color_le.fit_transform(X[:, 0] )
>>> X
array([[1, 1, 10.1],
	   [2, 2, 13.5],
	   [0, 3, 15.3]], dtype=object)
```

```python
>>> pd.get_dummies (df [ ['price', 'color', 'size' ] ] )
	price size color_blue color_green color_red
0   10.1   1        0          1           0
1   13.5   2        0          0           1
2   15.3   3        1          0           0
```

## ss