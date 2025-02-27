
| Excercise                 | prev. lecture                                                   | next lecture                                                            |
| ------------------------- | --------------------------------------------------------------- | ----------------------------------------------------------------------- |
| [[ML AI Modul7 Exercise]] | [[MachineLearning AI Modul 6\|Data preprocess. and hyperparam]] | [[MachineLearning AI Modul 8\|8. Intro to Reinforcement Learning (RL)]] |
# Multilayer Artificial Neural Networks
## Multilayer Perceptron
> [!NOTE] **ELI5:** MLP
> - **Feed forward, fully connected**
> - Input layer $\to$ hidden layer $\to$ output layer
> - if $\text{hidden layers}>1,$ then we call it *Deep Artificial Neural Network*  
> - \# of neurons in the hidden layer follows a pyramid structure 
>   (i.e. *wide at base $\to$ narrow at tip*)
>	- First layer is often chosen to be 16 or 64
### Activating neural networks via forward propagation.

#### **the MLP learning procedure in 3 steps:**
1. Starting at the input layer, we **forward propagate the patterns of the training data through the network to generate an putput.**
2. Based on the network's output, we calculate the error that we want to minimize using a cost function that we will describe late (\_\_\_\_\_\_)
3. We back propagate the error, find its derivative with respect to each weight in the network, and update the model.

##### **Step 1:** calculating the activation unit of the hidden layer $a_{1}^{h}$ as follows:
$$z_{1}^{(h)} = a_{0}^{(in)}w_{0,1}^{(h)}+a{1}^{(in)}w_{1,1}^{(h)}+\dots+a_{m}^{(in)}w_{m,1}^{(h)}$$ $$ø(z)=\frac{1}{1+e^{-z}}$$
![[Pasted image 20241028130931.png]]

