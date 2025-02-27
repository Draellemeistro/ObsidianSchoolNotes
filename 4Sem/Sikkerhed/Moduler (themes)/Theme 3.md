slides her

# [[encryption]]
 This theme consists of two main parts: (1) [[secret key encryption]] and (2) [[public key encryption]]. During the lecture will discuss some key concepts regarding different encryption modes, and small hands-on tasks related to [[Caesar Cipher]], [[One Time Pad]], etc. Then, we will discuss about different [[attacks against encryption systems]].

## Summary
### The type of operations used for transforming plaintext to ciphertext
- ==**Substitution**== ([[Caesar Cipher]] , [[Frequency analysis]]): Each element in the plaintext is mapped into another element
- **Transposition** ([[Transposition Cipher]], [Caesar Box Cipher](<https://gchq.github.io/CyberChef/#recipe=Caesar_Box_Cipher(4)>)): Elements in the plaintext are rearranged; Fundamental requirement is that no information should be lost
- ***Product systems**: Involve multiple stages of substitutions and transpositions*

### The way in which the plaintext is processed
- **[[Stream Cipher]]**: processes the input elements continuously, producing output one element at a time, as it goes along
	- ([[One Time Pad (OTP)]], **XORing**)
- **[[Block Cipher]]**: processes the input one block of elements at a time, producing an output block for each input block
	- ([[Feistel Cipher|Feistel Cipher structure]], [[Electronic Code Book (ECB)|ECB]], [[Cipher Block Chaining (CBC)|CBC]])

### The number of keys used
- **[[Symmetric Encryption|Symmetric]]**: if both sender and receiver use the same key
	- ([[Data Encryption Standard (DES)|DES]] , [[AES]])
- **[[Assymmetric Encryption aka public Key Encryption|Asymmetric (or public-key encryption)]]**: if the sender and receiver each use a different key
	- ([[RSA (Rivest, Shamir and Adleman 1978)|RSA]] , [[Diffie Hellman]])
#TODO where to put this? [[No-Key Protocol (Shamir)]]

## Assignments
- [[Assignment XOR]]
	- aflever [Theoretical assignment](https://www.moodle.aau.dk/mod/assign/view.php?id=1713383)
- [[Assignment Authentication and key agreement]]
	- aflever her: [python script](https://www.moodle.aau.dk/mod/assign/view.php?id=1713384)

## Before lecture
watch:
-  [Secret Key Exchange (Diffie-Hellman) - Computerphile](https://www.youtube.com/@Computerphile)
	- [Matematikken bag](https://www.youtube.com/watch?v=Yjrfm_oRO0w)
-  [Feistel Cipher](https://www.youtube.com/watch?v=FGhj3CGxl8I)
- [How did the Enigma Machine work?](https://www.youtube.com/@JaredOwen)

## Videoer
[[Diffie Hellman]]

[[Feistel Cipher]]

[[Caesar Cipher]]

# Slides
## Terminology
###  [[Encryption]] 
- **Plaintext**: original message
- **Ciphertext**: coded message
- **Cipher**: algorithm for transforming plaintext to ciphertext
- **Key**: secret information used in cipher known only to sender/receiver
- **Encipher (encrypt)**: converting plaintext to ciphertext
- **Decipher (decrypt)**: recovering plaintext from ciphertext
- **Cryptanalysis (code breaking)**: study of principles/methods of deciphering ciphertext without knowing key
