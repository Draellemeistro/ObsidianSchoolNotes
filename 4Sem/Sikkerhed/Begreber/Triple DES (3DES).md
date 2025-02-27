## Triple DES (3DES)
- Run [[Data Encryption Standard (DES)]] three times, each time using a different key
- 3 keys of 56 bits: $k_1k_2k_3$
- ciphertext =$E_{k3}(D_{k2}(E_{k1}(plaintext)))$
- plaintext = $D_{k1}(E_{k2}(D_{k3}(ciphertext)))$
![[Pasted image 20240220133539.png]]
