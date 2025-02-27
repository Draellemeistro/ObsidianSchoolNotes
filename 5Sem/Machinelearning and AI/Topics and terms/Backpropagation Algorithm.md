[Here](http://neuralnetworksanddeeplearning.com/chap1.html) we saw how neural networks can learn their weights and biases using the gradient descent algorithm. There was, however, a gap in our explanation: **We didn't discuss how to compute the gradient of the cost function.** Thats quite a gap!

backpropagation works far faster than earlier approaches to learning, making it possible to use neural nets to solve problems which had previously been insoluble. **Today, the backpropagation algorithm is the workhorse of learning in neural networks.**


> [!NOTE] **Backpropagation BS**
> At the heart of backpropagation is an expression for the partial derivative $\frac{∂C}{∂w}$ of the cost function $C$ with respect to any weight $w$ (or bias $b$) in the network.
> 
> The expression tells us how quickly the cost changes when we change the weights and biases. Therefore, backpropagation also supplies insights into how changing the weights and biases changes the overall behaviour of the network.
> ![[Backpropagation Algorithm.png]]
> 
> -  ;;;;;;; **NOTATIONS**
> - **for the networks biases and activations:**
> 	- **bias**: $b^{l}_{j}$ for the bias of the $j^{th}$ neuron in the $l^{th}$ layer
> 	- **activation**: $a^{l}_{j}$ for the activation of the $j^{th}$ neuron in the $l^{th}$ layer
> 	- ![[Backpropagation Algorithm-1.png]]
> - **with these notations,** the activation $a^{l}_{j}$ of the $j^{th}$ neuron in the $l^{th}$ layer is related to the activations in the $(l-1)^{th}$ by equation $$a^{l}_{j}=\sigma \left(\sum_{k}{w^{l}_{jk}a^{l-1}_{k}+b^{l}_{j}} \right),$$ Where the sum is over all neurons $k$ in the $(l-1)^{th}$  layer.
> 
> - **CAN BE REWRITTEN IN A MATRIX FORM (VECTORIZED??)**


> [!NOTE] **Rewriting backpropagation formula in vectorized**
> - Define a weight matrix $w^{l}$ for each layer, $l$
> 	- the entries are just the weights connecting to the $l^{th}$ layer of neurons
> 	- so, the entry in the $j^{th}$ row and $k^{th}$ column is $w^{l}_{jk}$
> - similarly, for each layer $l$ we define a bias vector, $b^{l}$
> 	- components of the bias vector are just $b^{l}_{j}$
> - finally, we define activation vector $a^{l}$ 
> 	- components of that is $a^{l}_{j}$
> - the last ingredient is the idea of vectorizing a function such as $\sigma$
> 	- The components of $\sigma(v)$ are just $\sigma(v)_{j}=\sigma(v_{j})$
> 
> $$a^{l}=\sigma(w^{l}a^{l-1}+b^{l})$$
> 
> When using this equation to compute $a^{l}$, we compute the intermediate quantity $z^{l}\equiv w^{l}a^{l-1}+b^{l}$ along the way. 
> - **which is useful enough to name!** $z^{l}$ is called the weighted input to the neurons in layer $l$
> 	- and sometimes our vectorized equation is written in terms of weighted input, as $a^{l}=\sigma(z^{l})$
> - **also worth noting:** $z^{l}$ has the components:
> $$z^{l}_{j}=\sum_{k}w^{l}_{jk}a^{l-1}_{k}+b^{l}_{j}$$
> That is, $z^{l}_{j}$ is just the weighted input to the activation function for neuron $j$ in layer $l$


## Two assumptions we need about the cost function
**For backpropagation to work we need to make two main assumptions about the form of the cost function.**

> [!NOTE] **The two assumptions**
> 11111111111111111111111111
> 1. the cost function can be written as an average $C=\frac{1}{n}\sum_{x}C_{x}$ over costfunction $C_{x}$ for individual train examples $x$.
> 	1. **reason:** what backpropagation actually lets us do is compute the partial derivatives $\frac{∂C_{x}}{∂w}$ and $\frac{∂C_{x}}{∂b}$ for a single training example. we then recover $\frac{∂C}{∂w}$ and $\frac{∂C}{∂b}$ by averaging over the examples.
> 2. cost can be written as a function of the outputs from the neural network:![[Backpropagation Algorithm-2.png]]

Here, for this example, we'll use the quadratic cost function.

> [!NOTE] quadratic cost function
> $$C = \frac{1}{2n} \sum_x \|y(x)-a^L(x)\|^2$$
> - $n$ total number of training examples; 
> - the sum is over individual training examples, $x;y=y(x)$ is the corresponding desired output
> - $L$ number of layers in the network
> - $a^{L}=a^{L}(x)$ is the vector of activations output from the network when $x$ is input


