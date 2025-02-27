![[Pasted image 20240220134226.png]]

- $c_i=E(m_i⊕c_{i-1},k)$
- Decryption $m_i=D(c_i,k)⊕c_{i-1}$
- Initialitation vector $c_0=IV$ (random number, not secret)

### Encryption
![[Pasted image 20240220134537.png]]
### Decryption
![[Pasted image 20240220134550.png]]
## Problems with CBC
- If you are **missing a block**, **can not decode** **the rest** of the chain
- It is slow, the process **cannot be parallelized**
- **==The attacker that corrupts one ciphertext can have impact/control the next message during the decryption==**
