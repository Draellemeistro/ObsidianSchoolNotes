
> [!NOTE] Types of [[Feature Scaling]]
> - **Normalization:** re-scales values in range 0-1
> - **Standardization:** scales features to have *mean = 0* and *std. deviation = 1* 


> [!NOTE] **Choice of scaler** (Normalization vs Standardization)
> Contents


```Python
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
sc.fit(X_train)
X_train_std = sc.transform(X_train)
X_test_std = sc.transform(X_test)
```
## Why do we need feature scaling?

> [!NOTE] **Lets look at an example:**
> 
> | # | Emp | Age | Salary |
> | - | --- | --- | ------ |
> | 1 | Emp1 | 44 | 73000 |
> | 2 | Emp2 | 27 | 47000 |
> | 3 | Emp3 | 30 | 53000 |
> | 4 | Emp4 | 38 | 62000 |
> | 5 | Emp5 | 40 | 57000 |
> | 6 | Emp6 | 35 | 53000 |
> | 7 | Emp7 | 48 | 78000 |
> 
> **Age range:** 27-48
> **Salary range:** 47000-78000
### Reasoning
In the above tanle we see that both **Age** and **Salary** have different range of values. So when we train a model. it might give high importance to salary column just because the high range of values

# Normalization: $x_{\text{norm}}=\frac{x-min(x)}{max(x)-min(x)}$
Also known as **min-max normalization** or **min-max scaling**
$x_{\text{norm}}=\frac{x-min(x)}{max(x)-min(x)}$

# Standardization: $x_{\text{stand}}=\frac{x-mean(x)}{\text{standard deviation}(x)}$
also known as **z-score Normalization**
![[image_Feature Scaling.png]]

# ifht. diagram i [[Data Preprocessing]]
## Data range-based scaling techniques
min-max normalization
## Data distribution-based data scaling techniques
 z-score normalization etc.
## Data structure-based data scaling techniques
logarithmic and sigmoidal methods etc.