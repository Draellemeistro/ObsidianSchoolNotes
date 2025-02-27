# [WHY YOU SHOULDN'T WRITE YOUR OWN ENCRYPTION ALGORITHM](https://keasigmadelta.com/blog/why-you-shouldnt-write-your-own-encryption-algorithm/)

{Date of Publish}: 10 Jan 2022
{Date of Note}:
{tags}:
{Related}:

## What was the most memorable thing about the text? (Main takeaways):
- Dårlige krypteringsalgoritmer er nemme at reverse-engineer
- ”*Even Experts Struggle to Create Bullet-Proof Algorithms*”
- ”*Algorithm Implementation Is Easy to Screw Up*”
	- ”*If you used the rand() function, then you've already screwed up. Rand() generates a **pseudo**-random number.*”
	- ”*you use memcmp() to check the password. Congratulations! You just created a ==**side-band leak==**.*”
		- Variations in code execution time allowed code to access memory that it wasn't supposed to have access to. It broke memory protection on a lot of CPUs.
- ”*If you are working on a server, passwords should be stored salted and hashed, using a currently recommended hashing algorithm. Do NOT write your own hash function, or use older ones with known vulnerabilities.*”
## What does it connect to?:

## What am i now interested in because of this text?:


## Textstykker
### cryptography 101
I bet your first idea for a super secure encryption algorithm would be to use a randomly generated string of numbers as key. Then, you'd add the key to incoming data on a per-byte basis, allowing it to overflow and wrap around. To be more sophisticated you might switch to a subtraction operation for some bytes, and maybe even add an XOR operation here or there.

The encrypted data would be a combination of the input data plus random noise. Perfect! or so you think...

Newsflash! You're not the first person to dream up this algorithm (or some variation thereof). It's crypto 101, and has been done before. Cryptography has been around far longer than modern computers. Such algorithms have been analysed, and possible weaknesses are known.