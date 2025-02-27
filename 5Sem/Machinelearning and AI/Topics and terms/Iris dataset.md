# Importing dataset
```Python
from sklearn import datasets
import numpy as np

# Importing the dataset
iris = datasets.load_iris()
X = iris.data[:, [2, 3]]
y = iris.target
print('Class Labels:', np/unique(y))
```

# Dividing into training and test sets
```Python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=1, stratify=y)
```
