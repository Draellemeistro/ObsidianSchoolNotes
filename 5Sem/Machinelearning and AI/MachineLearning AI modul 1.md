AI != Machine Learning

| Excercise | prev. lecture | next lecture                                                                          |
| --------- | ------------- | ------------------------------------------------------------------------------------- |
|           |               | [[MachineLearning AI modul 2\|Simple Machine Learning Algorithms for Classification]] |

# Introduction to Machine Learning
- [[Machine Learning tools]]
- [[Data Preprocessing]]
- [[Feature Extraction]] / Data cleaning
	- We want to save memory & simplify system
	- Some features are unnecessary for purpose
- in Deep learning computer does the training bcuz Neural Networks
- Data is the most importan. ==DATA UBER ALLES==
	- Training Data
	- Testing Data
	- Both are needed. Specific ratios will be determined through trial and error, and depends on model/data/purpose.
	- Always more training data than testing data.

- **Supervised learning** Desired output signals (predictive model) are already known
	- **goal:** Train model from labeled data in order to make predictions on future data.
	- **is good for:**
		- Binary classification
		- Machine translation
		- ==more!==
	- Classification
	- Regression
- **Semi-supervised learning**
	- Set training
- **Unsupervised learning** Explore structure of data to learn hidden information.
	- No labeled data: no guidance from known variable outcome. (**find similarities in data points**) ==CLUSTER THEM==
	- Clustering
	- If we don't have lever/label: we can ask human (**Human Expert**)
		- Can take a lot of time. Data sets are large, and humans are slow.
- **Reinforcement learning** (Trial and learn) Develop system that improves performance by interacting w. its enviroment to get reward (1: action, 2: reward, 3: Change state) System is called **the agent**
	- reinforces actions based on reward
	- **rewards:** *immediate*, *long-term*
		- Needs to be defined, but depends on objective function. what are we trying to get it to do well?
	- ==TEST IN SAME ENVIROMENT AS IT WAS TRAINED IN==
		- We cant transfer model from one domain to another
	- Q-learning
- 