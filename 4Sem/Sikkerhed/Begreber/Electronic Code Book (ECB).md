![[Pasted image 20240220134000.png]]

**==!!!!==** Sequence of messages $m_1, m_2,\dots,m_k$ is encrypted as $c_i=E(m_i,k)$

![[Pasted image 20240220134130.png]]

## Problems with ECB
- With ECB, if the same **b-bit block of plaintext appears more than once in the message**, **==it always produces the same ciphertext==**
- Because of this, **for lengthy messages**, the ECB mode ==**may not be secure**==
- If the message is highly structured, it may be possible for a cryptanalyst to **exploit these regularities**
![[Pasted image 20240220134838.png]]
