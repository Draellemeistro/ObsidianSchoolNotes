relevant in regards to [[Set Operations]] in [[Probability Theory 1 - Session 1]]
and [[the birthday attack]] in [[Theme 2]] of security

Se youtube-videoen linket under forberedelsen til [[Theme 2]] i security: [Vsauce: The Birthday Paradox](https://www.youtube.com/watch?v=ofTb57aZHZs)

# the general idea
there are about 365 days in a year. How many people need to be in a room before there’s a 50% chance that two of them share the same birthday?

If you have just **23 people** in a room, the odds of whether two get presents on the same day is a coin flip. Get 50 people together and that shared-birthday probability skyrockets to 97%. A handful more and it’s a virtual statistical certainty. see also this [Link](https://www.scientificamerican.com/article/bring-science-home-probability-birthday-paradox/#:~:text=Due%20to%20probability%2C%20sometimes%20an,Don't%20believe%20it's%20true%3F)

## explanation
23 people we have 253 pairs:
$$\frac{23*22}{2}=253$$
The chance of 2 people having different birthdays is:

$$ 1- \frac{1}{365} =\frac{364}{365}=.997260$$
making **253 comparisons** and having them _all_ be different is like getting heads 253 times in a row -- you had to dodge "tails" each time. Let's get an approximate solution by pretending birthday comparisons are like coin flips. (See Appendix A for the exact calculation.)

We use exponents to find the probability:
$$ \left( {\frac{364}{365}} \right) ^{253} = .4995  $$
![[Pasted image 20240212201026.png]]

$$ p(n) = 1- \left( {\frac{364}{365}} \right) ^{C(n,2)} = 1- \left( {\frac{364}{365}} \right) ^{n(n-1)/2}  $$
### Examples and takeaways
- $\sqrt{n}$ is roughly the number you need to have a 50% chance of a match with n items. $\sqrt{365}$ is about 20. this comes into play in cryptography for [[the birthday attack]]
- Even though there are $2^{128}(1e38)$ [[GUIDs]], we only have $2^{64}(1e19)$ to use up before a 50% chance of [[collision]]. 50% is high, really high.
- You only need 13 people picking letters of the alphabet to have 95% chance of a match.
- Exponential growth rapidly decreases the chance of picking unique items (aka it increases the chances of a match). Remember: exponents are non-intuitive and humans are selfish!
Se også: [A Repeated Multiplication Explanation](<https://betterexplained.com/articles/understanding-the-birthday-paradox/#:~:text=Appendix%20A%3A%20Repeated%20Multiplication%20Explanation%20(Exact%20Formula)>)
