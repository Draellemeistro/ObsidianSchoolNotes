

# Parametric vs non-parametric
> [!tip] **Parametric versus nonparametric models**
> Machine learning algorithms can be grouped into **parametric** and **nonparametric** models.
> ![[Pasted image 20240930092115.png]]

- **Parametric:** A model learning from the data, assuminga fixed number of parameters, regardless of the data size.
	- **examples:** regression, [[logistic regression]], [[Perceptron]]
	- **pros** fast and simple
	- **cons** maybe not complex enough
- **Non-Parametric:** The form of the underlying function is not assumed, giving the model more flexibility 
	- **Examples:** [[Support Vector Machines]], [[k-nearest neighbor (KNN)]], complex [[Multilayer Artificial Neural Networks|Neural Networks]] etc
	- **pros** allows for complexity (**)
	- **cons** can lead to overfitting (*the complexity leads us to learn the data too well*, e.g. [[Decision tree classifiers]])

# Different ML paradigms

> [!NOTE] The different paradigms
> - **[[Supervised Learning]]**
> 	- Labeled data
> 	- For classifying and predicting **new data**
> - **[[Unsupervised Learning]]**
> 	- Unlabeled data
> 	- Discover similarities and hidden connections in data
> 	- (*Can be used to gain insight in a dataset before utilizing [[Supervised Learning]]*)
> - **[[Reinforcement Learning]]**
> 	- No supervisor: only a reward signal
> 	- Delayed asynchronous feedback
> 	- Time is a factor
> 	- Agents earlier decisions affect later interactions

