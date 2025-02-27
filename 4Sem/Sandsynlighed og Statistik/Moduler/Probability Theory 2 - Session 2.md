# Random variables
## Before:
browse through [3.1.1](https://www.probabilitycourse.com/chapter3/3_1_1_random_variables.php), [3.1.2](https://www.probabilitycourse.com/chapter3/3_1_2_discrete_random_var.php), [3.1.3](https://www.probabilitycourse.com/chapter3/3_1_3_pmf.php), [4.1.0](https://www.probabilitycourse.com/chapter4/4_1_0_continuous_random_vars_distributions.php), [4.1.1](https://www.probabilitycourse.com/chapter4/4_1_1_pdf.php), [4.1.2](https://www.probabilitycourse.com/chapter4/4_1_2_expected_val_variance.php) from [PC](https://www.probabilitycourse.com/)

- [[random variables]]
- [[Discrete Random Variables]]
- [[Probability Mass Function (PMF)]]
- [[Continuous Random Variables and their Distributions]]
- [[Probability Density Function (PDF)]]
- [[Cumulative distribution function (CDF)]]
- [[Expected Value and Variance]]
- [[Jointly distributed random variables]]
- [[Independent random variables]]
## General overview of important shit
### Coinflip example

$$p(a)=P(X=a)$$

$p(x_{i})>0,i_{0}1,2,\dots$
$p(x)=0,otherwise$

- **CDF**
	- is defined for any real number x as the prob of the event $\{X\leq x\}$ 
		- $F(x)=P(X\leq x)$
	- F is funct of x
	- **==all prob questions about X can be answered in terms of its Distribution Function==**
	- example: $P(a<X\leq b)$
		- $\{X\leq b\}=\{X\leq a\}\bigcup\{a<X\leq b\}$
		- $P\{X\leq b\}=P\{X\leq a\}+P\{a<X\leq b\}$
		- $P\{a<X\leq b\}=F(b)-F(a)$
		- 


## Literature:
[chapter 3](https://www.probabilitycourse.com/chapter3/3_1_1_random_variables.php), [chapter 4](https://www.probabilitycourse.com/chapter4/4_0_0_intro.php), [chapter 5](https://www.probabilitycourse.com/chapter5/5_1_0_joint_distributions.php) from [PC](https://www.probabilitycourse.com/)  + [6.1.1](https://www.probabilitycourse.com/chapter6/6_1_1_joint_distributions_independence.php). and [6.1.2](https://www.probabilitycourse.com/chapter6/6_1_2_sums_random_variables.php). Note that not all subchapters are equally important. Please look at the lecture slides to see what topics we have been talking about.
## What we learn:
The concept of a [[random variables]] will be introduced. Two types of [[random variables]] are considered: discrete and continuous. We will learn how random variables can be specified using pmf/ pdf.  Special attention is given to jointly distributed r.v.s and independent r.v.s. Expectation and variance is introduced as key characteristics of a r.v. behaviour.
### Also
- What is a [[random variables|Random Variable]]?
- What types of random variables exists – how are they different and similar?
- How to work with distributions:
	- [[Sandsynlighed og Statistik/Begreber/Cumulative distribution function (CDF)]]
	- [[Probability Mass Function (PMF)]]
	- [[Probability Density Function (PDF)]]
- How to handle jointly distributed multiple random variables?
- How to define and work with expectation, variance and covariance
## Opgaver

### PDF med opgaver
![[Probability_Session2_Exercises.pdf]]

### PDF med svar
![[Probability_Session2_Solutions.pdf]]


## Lecture
### Topics
#### Discrete and continuous random variables.
ss
#### Probability mass function and probability density function.
ss
#### Cumulative distribution function.
ss
#### Jointly distributed random variables.
