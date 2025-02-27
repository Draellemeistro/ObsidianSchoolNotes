- Each party has a pair of keys: a **public key** and a **private key**.
- Knowing the public-key and the cipher, it is computationally infeasible to compute the private key
- ==**Many can encrypt, only one can decrypt**==
	- The **public key** can be given to **anyone** and is only used to **encrypt data**.
	- The **private key** is kept **secret** and is only used to **decrypt data**.
![[Pasted image 20240220140115.png]]
## Examples
### 1. RSA

> [!NOTE]  [[RSA (Rivest, Shamir and Adleman 1978)]]
>Based on difficulty of determining prime factors of large numbers

> [!NOTE] Questions
> How secure is RSA?
> What information can be made public and what information should be kept secret?

### [[Diffie Hellman|Diffie Hellman key exchange]]
- Purpose of the algorithm is to enable two users to exchange a secret key securely that then can be used for subsequent encryption of messages
- The algorithm itself is limited to the exchange of the keys
- Depends for its effectiveness on the difficulty of computing discrete logarithms

> [!NOTE] Questions
> - What information is publicly available?
> - Does [[Diffie Hellman|DH]] provide authentication?
> - Is a [[Man-ln-The-Middle (MlTM)|man-in-the-middle]] attack possible?

