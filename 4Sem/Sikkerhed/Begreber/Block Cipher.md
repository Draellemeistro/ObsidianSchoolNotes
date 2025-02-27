# Symmetric Block encryption algorithms
- [[Data Encryption Standard (DES)]]
- [[Triple DES (3DES)]]
- [[AES|Advanced Encryption Standard (AES)]]
- [[Blowfish]]
- [[RC5]]

## [[Feistel Cipher]] structure
#TODO ???

## [[Cipher block Modes of Operation]]
- A symmetric block cipher processes one block of data at a time
	- In the case of [[Data Encryption Standard (DES)]] and [[Triple DES (3DES)]], the block length is b=64 bits
	- For [[AES|Advanced Encryption Standard (AES)]], the block length is b=128
- For longer amounts of plaintext, it is necessary to break the plaintext into b bit blocks, **==padding==** the last block if necessary
- Different modes result in different security properties of the underlying block cipher:
	- [[Electronic Code Book (ECB)]]
	- [[Cipher Block Chaining (CBC)]]
	- Others: **Cipher Feedback (CFB)**, **Output Feedback (OFB)**, **Block Replay**, etc.


> [!NOTE] Question
> What is a problem in using [[Electronic Code Book (ECB)|Electronic Code Book]]?


> [!NOTE] Question
> What is a problem in using [[Cipher Block Chaining (CBC)|Cipher Block Chaining]]?





