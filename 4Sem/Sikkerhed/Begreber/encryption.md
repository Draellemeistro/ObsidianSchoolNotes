# Similar / Relevant topics
***Scramble data temporarily until a key is used to unscramble it***
[[public key encryption]]
[[secret key encryption]]
[[Steganography]]
[[CyberChef]] (useful resource)

## Videoer der kan være interessante eller hjælpe med forståelse
- [Storing Files in Minecraft](https://www.youtube.com/watch?v=z16rzIF5J40&t=6s): Kommer ind på **substitution ciphers** og **cracking af dem**
- 
# Terminology
- **Plaintext**: original message
- **Ciphertext**: coded message
- **Cipher**: algorithm for transforming plaintext to ciphertext
- **Key**: secret information used in cipher known only to sender/receiver
- **Encipher (encrypt)**: converting plaintext to ciphertext
- **Decipher (decrypt)**: recovering plaintext from ciphertext
- **Cryptanalysis (code breaking)**: study of principles/methods of deciphering ciphertext without knowing key
# The idea
**Encryption** converts plaintext to an encrypted form using an **encryption algorithm** E that outputs a **ciphertext**: $$Ciphertext = E_{key}(plaintext)$$
**Recipient** decrypts ciphertext C by means of a **decryption algorithm** D to get the **plaintext**: $$Plaintext = D_{key}(ciphertext)$$
- Picture
	- ![[Pasted image 20240220120952.png]]


> [!NOTE] Encryption & Decryption
> The security of encryption depends on the secrecy of the key, not the secrecy of the algorithm.

The **encryption** and **decryption algorithms** are chosen so that it is **==infeasible==** for someone other than Sender and Recipient to determine plaintext from ciphertext.

## History
- 1900 BC: Egypt
- 100 – 44 BC: Julius [[Caesar Cipher|Caesar]]
- World War I: [[One-Time Pad]]
- World War II: [[Enigma Machine]]

## Classification of Cryptographic systems
### The type of operations used for transforming plaintext to ciphertext
- ==**Substitution**== ([[Caesar Cipher]] , [[Frequency analysis]]): Each element in the plaintext is mapped into another element
- **Transposition** ([[Transposition Cipher]], [Caesar Box Cipher](<https://gchq.github.io/CyberChef/#recipe=Caesar_Box_Cipher(4)>)): Elements in the plaintext are rearranged; Fundamental requirement is that no information should be lost
- ***Product systems**: Involve multiple stages of substitutions and transpositions*
### The way in which the plaintext is processed
- **[[Stream Cipher]]** ([[One Time Pad (OTP)]]): processes the input elements continuously, producing output one element at a time, as it goes along
- **[[Block Cipher]]**: processes the input one block of elements at a time, producing an output block for each input block

### The number of keys used
- **[[Symmetric Encryption|Symmetric]]**: if both sender and receiver use the same key
- **[[Assymmetric Encryption aka public Key Encryption|Asymmetric (or public-key encryption)]]**: if the sender and receiver each use a different key
#TODO where to put this? [[No-Key Protocol (Shamir)]]

# Attacking an encryption system

> [!NOTE] Attackers objective:
> The objective of attacking an encryption system is to **==recover the key==** in use rather then simply to recover the plaintext of a single ciphertext
## Two general approaches
1. [[brute-force attack]]: The attacker tries every possible key on a piece of cipher text until an intelligible translation into plaintext is obtained.
2. [[Cryptoanalysis]]: Cryptanalytic attacks rely on the nature of the algorithm plus perhaps some knowledge of the general characteristics of the plaintext or even some sample plaintext-ciphertext pairs. This type of attack exploits the characteristics of the algorithm to attempt to deduce a specific plaintext or to deduce the key being used.
## Common attack models
- **Ciphertext-only** attack:
	- Given many ciphertexts. Can you find out the key?
- **Known-plaintext** attack:
	- Given one or many pairs of plaintext and ciphertext. Can you find out the key? Can you find out the other plaintexts that I did not tell you?
- **Chosen-plaintext** attack:
	- You decide the plaintext. You can give me your plaintext. I will encrypt it using my secret key and give you back the ciphertext. You can provide as many plaintext as you want, I will give you the ciphertext. Given these choosen plaintext and ciphertext, can you find out my secret key or can you find out other secret plaintext?
## Computationally secure scheme
- The cost of breaking the cipher exceeds the value of the encrypted information
- The time required to break the cipher exceeds the useful lifetime of the information
