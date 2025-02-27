## Fra forelæsning
**$P(X = a)= p(a)$**
Sum of  all  prob. over all must be = 1 for discrete [[random variables|r.v.]]
becomes sum for continuous [[random variables|r.v.]] (see it as a generalization [[Probability Density Function (PDF)|PDF]]) (we introduce [[Density]])
![[Pasted image 20240218154100.png]]
![[Pasted image 20240218154128.png]]

## Joint PMF
![[Pasted image 20240218161107.png]]
![[Pasted image 20240218161122.png]]
### Conditional pmf
![[Pasted image 20240218161732.png]]
![[Pasted image 20240218161916.png]]
## Fra hjemmeside
> [!NOTE] Properties of PMF:
> - $0 <= P_X(x) <= 1$ for all x;
> - $∑_{x∈R_X}P_X(x)=1$
> - For any set $A⊂R_X,P(X∈A)=∑_{x∈A}P_X(x)$

If X is a discrete [[random variables]] then its range **Range(X)** or $R_X$ is a countable set, so, we can list the elements in $R_X$. In other words, we can write: $$R_X =\{x_1, x_2, x_3, \dots\}$$
$x_1, x_2, x_3, \dots$ are possible values of the [[random variables]] X. While random variables are usually denoted by capital letters, to represent the numbers in the range we usually use lowercase letters for a discrete [[random variables]] X, we are interested in knowing the probabilities of $X = x_k$. Note that here, the event $A = \{X = x_k\}$ is defined as the set of outcomes *s* in the sample space *S* for which the corresponding value of *X* is equal to $x_k$$. In particular, $$A = \{s ∈ S|X(s) = x_k\}$$The probabilities of events $\{X = x_k\}$ are formally shown by the **probability mass function (pmf)** of *X*.

> [!NOTE] Title
> Let *X* be a discrete [[random variables|random variable]] with range $R_X =\{x_1, x_2, x_3, \dots\}$ (finite or countably infinite). The function $$P_X(x_k) = P(x = x_k), for k =1, 2, 3, \dots,$$ is called the _probability mass function (PMF)_ of *X*

the PMF is a probability measure that gives us probabilities of the possible values for a random variable. While the above notation is the standard notation for the PMF of *X*, it might look confusing at first. The subscript *X* here indicates that this is the PMF of the random variable *X*. Thus, for example, $P_X(1)$ shows the probability that $X = 1$. 

Although the PMF is usually defined for values in the range, it is sometimes convenient to extend the PMF of X� to all real numbers. If x ∉ $R_X$, we can simply write $P_X(x) = P(X = x) = 0$. Thus, in general we can write 
					$\{ P(X = x)  if-x-is-in-R_X$ 
		$P_X(x) = \{$ 
					$\{ 0 - otherwise$

![[Pasted image 20240215185900.png]]

For discrete random variables, the PMF is also called the **probability distribution**. Thus, when asked to find the probability distribution of a discrete random variable X, we can do this by finding its PMF. The phrase _distribution function_ is usually reserved exclusively for the cumulative distribution function CDF (as defined later in the book). The word _distribution_, on the other hand, in this book is used in a broader sense and could refer to PMF, probability density function (PDF), or CDF.
### Example
I toss a fair coin twice, and let X be defined as the number of heads I observe. Find the range of $X, R_X$, as well as its probability mass function $P_X$.
