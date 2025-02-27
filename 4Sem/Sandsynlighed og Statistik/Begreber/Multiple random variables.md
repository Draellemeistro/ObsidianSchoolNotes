# Multiple random variables
### Joint functions
**to specify the relationship between two r.v., we dfefine the [[joint CDF]]**
If X and Y are **discrete r.v.'s** we define **[[joint PMF]]**
for **continous r.vs.** we define **[[joint PDF]]**


> [!NOTE] something
> let $X_{1},\dots,X_{n}$ be the **jointly distributed random variables**
> Definitions for [[Probability Mass Function (PMF)|PMF]] , [[Probability Density Function (PDF)|PDF]] , [[Cumulative distribution function (CDF)]] (eller er det [[joint PMF]], [[joint PDF]] , [[joint CDF]])
> **they can be generalized to a case of *n* [[random variables|r.v.s]] for example:**
> **the joint cumulative distribution function ([[joint CDF|here]]) is defined as**
> $$F(x_{1},\dots,x_{n})=P(X_{1}\leq x_{1},\dots,X_{n}\leq x_{n})$$


### Conditional distributions
- **The relationship between two random variables can often be clarified by consideration of the conditional distribution of one given the value of the other.**
- the **[[conditional PMF]]** of **X** given that **Y**=*y* is defined by: **==!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!==**
  $$p_{X|Y}(x|y)=\frac{p(x,y)}{p_{Y}(y)}$$
- If X and Y have a **[[joint PDF]]**, then the **[[conditional PDF]]** of **X** given that **Y**=*y* is defined as
  **==!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!==**
  $$f_{X|Y}(x|y)=\frac{f(x.y)}{f_{Y}(y)}$$
##### Example conditional Distributions
**[[joint PMF]] of X and Y is given:**

| X\Y         | 0   | 1   | x-probs |
| ----------- | --- | --- | ------- |
| **0**       | 0.4 | 0.1 | 0.5     |
| **1**       | 0.2 | 0.3 | 0.5     |
| **y-probs** | 0.6 | 0.4 |         |
**Calculate the [[conditional PMF]] of X given that Y=1:**
$$P\{X=0|Y=1\}=\frac{p(0,1)}{P\{Y=1\}}=\frac{0.2}{0.5}=0.4$$
$$P\{X=1|Y=1\}=\frac{p(1,1)}{P\{Y=1\}}=\frac{0.3}{0.5}=0.6$$

### General Stuff
- So far, we were speaking about calculation of probabilities of events involving a single r.v. in isolation. Now we will look at the techniques for probability calculations of events that involve the joint behavior of two or more r.v.
	- The relationship between two random variables can often be clarified by consideration of the conditional distribution of one given the value of the other.
- **Example**: height, weight and age of a person from a group
![[Pasted image 20240218161235.png]]
No, we need more information(such as ==independence==). For understanding, see this image:
	![[Pasted image 20240218161327.png]]
![[Pasted image 20240602163842.png]]![[Pasted image 20240602163855.png]]