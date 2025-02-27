Based on difficulty of determining prime factors of large numbers



## Approach
- Select secret primes p, q (>100 decimal digits) 
- Calculate n=p*q
- Calculate $\phi$(n) = (p-1)(q-1)
- Choose encryption key e, such that e and $\phi$(n) do not have common factors
- Calculate decryption key d: d*e mod $\phi$(n) = 1

## Simple example of RSA
Let's say Alice wants to send a secure message to Bob using RSA.

### Key generation
- Bob chooses p = 3 and q = 11 (in practice, much larger primes are used).
- Bob calculates n = p * q = 33
- Bob Calculates $\phi$(n) = (p-1)(q-1) = 2 * 10 * 10
- Bob chooses encryption key e = 3 (which is coprime with $\phi$(n) = 20
- Bob calculates decryption key d = 7 (since 3 * 7 = 21), which is 1 mod 20.
- Bob’s public key is (e = 3, n = 33)
- Bob’s private key is (d = 7, n = 33)
### Encryption
Alice wants to send the message M = 7.
She uses Bob's public key to encrypt the message: $C=M^e modn = 7^3mod33 =343 mod33 = 13$
- Matematikken, hvis forvirring:
	![[Pasted image 20240220140827.png]]

### Decryption
Bob receives C = 13.
He uses his private key to decrypt the message: $M=C^d modn = 13^7 mod33 = 7$
Bob successfully decrypts Alice’s message, which is 7.