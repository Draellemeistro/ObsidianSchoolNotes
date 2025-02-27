- Key MUST be truly random
- Key must be at LEAST as long as the message to be encrypted
- **==Key must be used only once==**. Never reuse the key.

- Provably Perfectly secure – cannot be cracked
- However, it suffers from key management problem


> [!NOTE] Important note:
> **One-time pads** or **one-time encryption** is **==NOT==** to be confused with [[one-time keys (OTK)]] or [[one-time passwords (OTP)]].

- The weak point of the *XOR* operation is that ***XOR* is its own inverse**: **A** ⊕ **B** ⊕ **A** = **B**.
- When you know the part of the plaintext message M for the corresponding encrypted message C, you immediately obtain that part of the key as K = M ⊕ C.
## How it works:
### 1. Generate the key, at least as long as the plaintext
key = $k_1, k_2, k_3, k_4...$ (random, used one-time only)
### 2. Plaintext = $m_1,m_2, m_3, m_4...$

### 3. Ciphertext= $c_1c_2c_3c_4...$ where $c_i=m_i⨁k_i$ 
- Example:
	![[Pasted image 20240220131750.png]]

## lets try
### xor.py
```python
#!/usr/bin/python3

# XOR two bytearrays
def xor(first, second):
   return bytearray(x^y for x,y in zip(first, second)) 

MSG   = "A message"
HEX_1 = "aabbccddeeff1122334455"
HEX_2 = "1122334455778800aabbdd"

# Convert ascii string to bytearray
D1 = bytes(MSG, 'utf-8')

# Convert hex string to bytearray
D2 = bytearray.fromhex(HEX_1)
D3 = bytearray.fromhex(HEX_2)
  
r1 = xor(D1, D2)
r2 = xor(D2, D3)
r3 = xor(D2, D2)
print(r1.hex())
print(r2.hex())
print(r3.hex())
```
