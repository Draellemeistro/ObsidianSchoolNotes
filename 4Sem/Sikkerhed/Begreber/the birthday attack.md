When you make a password, that password is [[Hashing|Hashed]] into a Digest or hash value. when the md5 hashing algorithm was widely used, its 128-bit 32 hexadecimal hashes were vulnerable to hacking based on the [[Birthday paradox]]. 
The idea was to find a [[Collision]] where two hashes has the same value regardless of input, and therefore learn how it works.
The $3.4 * 10^{38}$ possible outcomes of md5 was cracked used an algorithm based on the math of probabilities displayed in the [[Birthday paradox]] 

## from [[Theme 2]]

Let’s assume there are N people in a given room. What is the probability that nobody shares a birthday?
![[Pasted image 20240215154819.png]]
This is the probability that we do not have any matches in a group of N people:
![[Pasted image 20240215154834.png]]

Let’s assume there are N people in a given room. What is the probability that at least 2 people share the same birthday?
![[Pasted image 20240215154855.png]]
This is the probability that there is at least 2 people with the same bithday in a group of N people:
![[Pasted image 20240215154909.png]]

Let’s assume there are N people in a given room. What is the probability that at least 2 people share the same birthday with 50% probability?![[Pasted image 20240215154924.png]]
It turns out to be that N=23. This means that even with a small group of people, it is quite common for at least 2 people to share the same birhday