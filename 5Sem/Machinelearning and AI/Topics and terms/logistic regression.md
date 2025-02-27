> [!NOTE] **Illustration of the model**
> ![[image_logistic regression-1.png]]
> 
> **So, whats the difference???**
> look at the activation function. It attempts to improve on [[Adaline]] by smoothing out the activation function. (*this allows, us to easier see how updating the weights affects output*)

# Sigmoid function
The **logistic sigmoid function**, often simply abbreviated as **sigmoid function** due to its characteristic S-shape: $$\phi(z)=\frac{1}{1+e^{-z}}$$
$$z=\bar{w}^{T}\bar{x}=w_{0}x_{0}+\dots+w_{m}x_{m}$$

> [!NOTE] predicted value ( $\hat{y}$ )
> $$\hat{y}=\begin{cases}
1 & \text{if }\phi(z)\geq 0.5 \\
0 & otherwise
\end{cases}$$
. 
![[image_logistic regression-2.png]]

![[image_logistic regression-3.png]]

# Learning the weights of the logistic cost function

## The likelihood $L$ that we want to max when we build a [[logistic regression]] model
$$L(\bar{w})=P(\bar{y}|\bar{x};\bar{w})=$$
$$\prod_{i=1}^{n}P\big( y^{(i)}|\bar{x}^{(i)};\bar{w}\big)=$$
$$\prod_{i=1}^{n}\big( \phi(z^{(i)})\big)^{y^{(i)}}\big( 1-\phi(z^{(i)}) \big)^{1-y^{(i)}}$$

## The cost function
$$J(\bar{w})=\sum_{i=1}^{n}\big[ -y^{(i)}\log(\phi(z^{(i)}))-(1-y^{(i)})\log(1-\phi(z^{(i)})) \big]$$
$$J(\phi(z),y;\bar{w})= -y\log(\phi(z^{(i)}))-(1-y)\log(1-\phi(z))$$
$$J(\phi(z),y;\bar{w})= \begin{cases}
-\log(\phi(z)) & \text{if } y=1 \\
-\log(1-\phi(z)) & \text{if } y=0
\end{cases}$$
![[image_logistic regression-4.png]]
## Updating the weights
$$\Delta w_{j}=-\eta\frac{∂J}{∂w_{j}} = \eta \sum_{i=1}^{n}\big( y^{(i)}-\phi(z^{(i)})\big)x_{j}^{(i)}$$
$$\bar{w}=\bar{w}+\Delta \bar{w}, \Delta \bar{w}=-\eta \nabla J(\bar{w})$$

# Training a [[logistic regression]] model with scikit-learn
```Python
from sklear.linear_model import LogisticRegression
lr - LogisticRegression(C=100.0, random_state=1)
lr.fit(X_train_std, y_train)
plot_decision_regions(X_combined_std, y_combined,classifier=lr, test_idx=range(105,150))
plt.xlabel('ssss')
plt.ylabel('aaaa')
plt.show()
```
![[image_logistic regression-5.png]]

# Tackling [[overfitting and underfitting|overfitting]] via regularization

Take this big ol' bitch of an equation $$J(\bar{w})=\sum_{i=1}^{n}\big[ -y^{(i)}\log(\phi(z^{(i)}))-(1-y^{(i)})\log(1-\phi(z^{(i)})) \big]$$
and simply add a $\frac{\lambda}{2}\|w\|^2$ at the end:
$$J(\bar{w})=\sum_{i=1}^{n}\big[ -y^{(i)}\log(\phi(z^{(i)}))-(1-y^{(i)})\log(1-\phi(z^{(i)})) \big]+\frac{\lambda}{2}\|w\|^2$$
![[image_logistic regression-6.png]]