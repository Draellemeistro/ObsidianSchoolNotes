
> [!NOTE] Perceptron **Learning Rule**
> 1. init the weights to 0 or very small random numbers
> 2. For each training sample $x^{(i)}$:
> 	1. Compute the output value $\hat{y}$
> 	2. update the weights
> ![[Perceptrons.png]]

# Perceptron for [[Classification]]
## Weight Update
$$w_{j}:=w_{j}+\Delta{w_{j}}$$
$$\Delta{w_{j}}=\eta \big( y^{(i)}-\hat{y}^{(i)}\big)x^{(i)}_{j}$$
- $\eta:$ Learning rate
- $y^{(i)}:$ True class label
- $\hat{y}^{(i)}:$ Predicted class label (*output of the model*)
- $x^{(i)}:$  training sample 


> [!NOTE] **Weight Update:** Example
> $$\Delta{w_{j}}=\eta \big(-1-(-1)\big)x^{(i)}_{j}=0$$
$$\Delta{w_{j}}=\eta \big(1-1\big)x^{(i)}_{j}=0$$

In the case  of a wrong prediction, the weights are being pushed towards the direction of the positive or negative target class:
$$\Delta{w_{j}}=\eta \big(1--1\big)x^{(i)}_{j}=\eta(2)x^{i}_{j}$$
$$\Delta{w_{j}}=\eta \big(-1-1\big)x^{(i)}_{j}=\eta(-2)x^{i}_{j}$$
![[Perceptrons-1.png]]


# Using [[Perceptron|Perceptrons]] in python

## [[Iris dataset]] example

```Python
from sklearn.linear_model import Perceptron
ppn =Perceptron(n_iter=40, eta=0.1, random_state=1)
# if you've don feature scaling (else just ppn.fit(X_train, y_train))
ppn.fit(X_train_std, y_train)

y_pred = ppn.predict(X_test_std)

from sklearn.metrics import accuracy_score
print('Misclassified samples: %d' % (y_test != y_pred).sum())
print('accuracy: %.2f' % accuracy_score(y_test, y_pred))
```