Like the [[Perceptron]], a type of single-layer neural network: **ADAptive linear Neuron** (Adaline)
# For Classification
We can define the [[cost functions]] $J$ to learn the weights as the **Sum of Squared Errors (SSE)** between calculated outcome and the true class label (calculated outcome: $??$, true class label: $y^{(i)}$): $$J(w)=\frac{1}{2}\sum_{i}\big( y^{(i)}-\phi(z^{(i)})\big)^2$$

> [!NOTE] **[[Adaline]]** Weight Update
> ![[image_Adaline-1.png]]
> $$w:= w + \Delta w$$
$$\Delta w = -\eta \nabla J(w)$$
$$\Delta w_{j}= -\eta \frac{∂J}{∂w_{j}} = \eta \sum_{i}\big( y^{(i)}-\phi(z^{(i)})\big)x^{(i)}_{j}$$
$$\Delta w_{j}= -\eta \frac{∂J}{∂w_{j}} = \eta \sum_{i}\big( y^{(i)}-\phi(z^{(i)})\big)x^{(i)}_{j}$$
