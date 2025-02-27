In essence, a random variable is a real-valued function that assigns a numerical value to each possible outcome of the random experiment. **We usually show random variables by capital letters such as X, Y, and Z**


> [!NOTE] HOW TO: describe random variables
> [[Probability Mass Function (PMF)|PMF]] [[Probability Density Function (PDF)|PDF]] <----> [[Cumulative distribution function (CDF)|CDF]]
> ![[Pasted image 20240602152518.png]]
> ![[Pasted image 20240602152530.png]]

## most importnat

> [!NOTE] Videos:
> [Discrete Random Variables-1](https://www.youtube.com/watch?v=uSKBYIuzZfU&t=5s)
> Continuous

![[Pasted image 20240218154014.png]]
![[Pasted image 20240218154030.png]]

### see:
- [[Cumulative distribution function (CDF)]]
- [[Probability Mass Function (PMF)]]
- [[Probability Density Function (PDF)]]
- [[Random variables Key Performance Indicators]]
* Joint CDF, PMF, PDF
	* Conditional PMF, PDF, CDF(?)
![[Pasted image 20240218155426.png]]
![[Pasted image 20240218160839.png]]



> [!NOTE] Types of r.v.
> - **discrete**
> 	- [[Probability Mass Function (PMF)|PMF]] p(x)
> 	  $P\{a<X<b\}=\sum_{x_{i}\in(a,b)}p(x_{i})$
> - **continuous**
> 	- [[Probability Density Function (PDF)|PDF]] f(x)
> 	  $P(a\leq X\leq b)=\int_{a}^{b}  \, f(x)dx$
> - **mixed**
> 


[[Multiple random variables]]

### Independent r.v. [[Independence and r.v]]
![[Pasted image 20240218161504.png]] 

## Example: Coin toss
toss a coin five times. This is a random experiment and the sample space can be written as:
$$S = \{TTTTT,TTTTH,\dots ,HHHHH\} $$

> [!NOTE] Note:
> Here, the sample space *S* has $2^{5}=32$ elements. Suppose that in this experiment, we are interested in the number of heads. We can define a random variable *X* whose value is the number of observed heads. The value of *X* will be one of 0, 1, 2, 3, 4 or 5 depending on the outcome of the random experiment.


> [!NOTE] Random Variables:
> A random variable ***X*** is a function from the sample space to the real numbers.
> $X : S → R$

### Range
Since a random variable is a function, we can talk about its range. The range of a random variable X, shown by **Range(X)** or $R_X$, is the set of possible values for X. In the above example **Range(X)** =$R_X$ = {0, 1, 2, 3, 4, 5}. 

# important classes of random variables
There are two important classes of random variables that we discuss: **_discrete random variables_** and **_continuous random variables_**.
There will be a third class of random variables that are called ***mixed random variables***. as the name suggests, can be thought of as mixture of discrete and continuous random variables.
## Discrete

> [!NOTE] Remember
> a set A is countable if either:
> - A is a finite set such as {1, 2, 3, 4}, or
> - it can be put in one-to-one correspondence with natural numbers (in this case the set is said to be countably infinite)

==**A random variable is discrete if its range is a countable set**==
## Continuous 
One big difference that we notice here as opposed to discrete random variables is that the [[Sandsynlighed og Statistik/Begreber/Cumulative distribution function (CDF)|Cumulative distribution function (CDF)]] is a continuous function, i.e., it does not have any jumps. Remember that jumps in the [[Cumulative distribution function (CDF)|CDF]] correspond to points *x* for which $P(X = x) > 0$. Thus, the fact that the [[Cumulative distribution function (CDF)|CDF]] does not have jumps is consistent with the fact that $P(X = x) > 0$ for all *x*. **we have the following definition for continuous random variables.** 
> [!NOTE] Random Variables:
> A random variable ***X*** with  [[Cumulative distribution function (CDF)|CDF]] $F_X(x)$ is said to be continuous if $F_X(x)$ is a continuous function for all x ∈ R.

==We will also assume that the CDF of a continuous random variable is differentiable almost everywhere in R==

# Mixed
## Example of a mixed r.v.
The delay (= waiting time in a queue) for a packet transmission is zero if the queue is empty, and if the queue is not empty, the delay is an exponentially distributed r.v. with [[Cumulative distribution function (CDF)|CDF]]
$$F(x)=1-e^{-\lambda x}$$
The probability that the queue is empty is **p** and busy **1-p**
[[Cumulative distribution function (CDF)|CDF]] of the delay X:
$$F(x)=P(X\leq x)=P(X\leq x|idle)*p+P(X\leq x|busy)*(1-p)=$$
$$=p+(1-p)(1-e^{-\lambda x})$$
