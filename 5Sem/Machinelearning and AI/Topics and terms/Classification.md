
> [!NOTE] **[[Perceptron]]** vs **[[Adaline]]** vs **[[logistic regression]]**
> **LOOK AT ACTIVATION FUNCTION!**
> - **Perceptron** NO ACTIVATION FUNCTION
> 	- ![[Classification.png]]
> - **Adaline** LINEAR ACTIVATION FUNCTION
> 	- ![[Classification-1.png]]
> - **Logistic Regression** SIGMOID ACTIVATION FUNCTION
> 	- ![[image_Classification-3.png]]


# [[Perceptron]] for Classification

# [[Adaline]] for Classification
![[image_Classification-2.png]]

> [!NOTE] **[[Adaline]]** Weight Update
> **cost function:** Sum of Squared Errors (SSE) between calculated outcome and true class label
> 
> ![[image_Classification.png]]
> $$w:= w + \Delta w$$
$$\Delta w = -\eta \nabla J(w)$$
$$\Delta w_{j}= -\eta \frac{∂J}{∂w_{j}} = \eta \sum_{i}\big( y^{(i)}-\phi(z^{(i)})\big)x^{(i)}_{j}$$
$$\Delta w_{j}= -\eta \frac{∂J}{∂w_{j}} = \eta \sum_{i}\big( y^{(i)}-\phi(z^{(i)})\big)x^{(i)}_{j}$$
  .
 **(BIG ARROW) leads to this:**
 ![[image_Classification-1.png]]
 
 [[Gradient Descent]]

