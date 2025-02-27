- One of the simplest encryption techniques
- **Substitution cipher**: each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet
## Example:
Caesar cipher using a right rotation of three places ==Deciphering== is done in reverse, with a **left shift of 3**.

- Encryption and Decryption of a plaintext letter p, substitute the cipher text letter c by a shift k:
	$E_n(p) = (p+k)mod26$
	$D_n(c)=(c-k)mod26$
	Where A → 0, B → 1, ..., Z → 25 and 1$\leq$ k $\leq$ 25
- The algorithm is not secret → ==The key is secret==
- Easy to guess using ”**frequency analysis**”
#### CaesarCipher.py
```python
def caesar_encrypt(plaintext, shift):
    """Encrypts plaintext using the Caesar cipher."""
    encrypted_text = ""
    for char in plaintext:
        # Encrypt uppercase characters
        if char.isupper():
            encrypted_text += chr((ord(char) + shift - 65) % 26 + 65)    
        # Encrypt lowercase characters
        elif char.islower():
            encrypted_text += chr((ord(char) + shift - 97) % 26 + 97)
        # If it's not an alphabet, add it as it is
        else:
            encrypted_text += char

    return encrypted_text

  
# Ask for user input
message = input("Enter your message: ")
shift = int(input("Enter the shift key: "))

# Encrypt the message
encrypted_message = caesar_encrypt(message, shift)


print("Encrypted message:", encrypted_message)
```


## ROT13 (Rotate by 13 places)
- Special case of Caesar cipher
- Replaces a letter with the 13th letter after it in the **latin** **alphabet**.
- **Billedeksempel:**
	![[Pasted image 20240220123054.png]]

### Let’s try

Decrypt the message “**Aopz pz hu lujyfwalk zaypun!**” using ROT13
[CyberChef Onlineredskab](https://gchq.github.io/CyberChef)
- **output**:
	Amount =  1: Bpqa qa iv mvkzgxbml abzqvoî
	Amount =  2: Cqrb rb jw nwlahycnm bcarwpî
	Amount =  3: Drsc sc kx oxmbizdon cdbsxqî
	Amount =  4: Estd td ly pyncjaepo dectyrî
	Amount =  5: Ftue ue mz qzodkbfqp efduzsî
	Amount =  6: Guvf vf na rapelcgrq fgevatî
	Amount =  7: Hvwg wg ob sbqfmdhsr ghfwbuî
	Amount =  8: Iwxh xh pc tcrgneits higxcvî
	Amount =  9: Jxyi yi qd udshofjut ijhydwî
	Amount = 10: Kyzj zj re vetipgkvu jkizexî
	Amount = 11: Lzak ak sf wfujqhlwv kljafyî
	Amount = 12: Mabl bl tg xgvkrimxw lmkbgzî
	Amount = 13: Nbcm cm uh yhwlsjnyx mnlchaî
	Amount = 14: Ocdn dn vi zixmtkozy nomdibî
	Amount = 15: Pdeo eo wj ajynulpaz opnejcî
	Amount = 16: Qefp fp xk bkzovmqba pqofkdî
	Amount = 17: Rfgq gq yl clapwnrcb qrpgleî
	Amount = 18: Sghr hr zm dmbqxosdc rsqhmfî
	**==Amount = 19: This is an encrypted stringî==**
	Amount = 20: Uijt jt bo fodszqufe tusjohî
	Amount = 21: Vjku ku cp gpetarvgf uvtkpiî
	Amount = 22: Wklv lv dq hqfubswhg vwulqjî
	Amount = 23: Xlmw mw er irgvctxih wxvmrkî
	Amount = 24: Ymnx nx fs jshwduyji xywnslî
	Amount = 25: Znoy oy gt ktixevzkj yzxotmî
**==Amount = 19: This is an encrypted stringî==**
### [[Frequency analysis]] in English language
![[Pasted image 20240220124946.png]]
![[statSLET.png]]
If you have the frequency analysis on the ciphertext, you can guess what combination in the ciphertext mapped to the origin text.
- Think about the frequencies of letters in [[Frequency analysis|English]]: **E T A O I N S** are the most frequently used letters
- Some short words area frequent and easy to recognize: **a, I, to, on, the**... etc
- Use this knowledge to progressively figure out the key
### Let’s try Frequency analysis (Independent work)
- Ciphertext file: **ciphertext.txt**
- Calculate frequency: python **frequency.py**
Replace the characters to find the plaintext:
**==Example==**: tr ntyhqu EHTRSN < **ciphertext.txt**
 
> [!NOTE] filer
> Ligger på Moodle under Theme 3: encryption ([link til scripts](https://www.moodle.aau.dk/mod/resource/view.php?id=1713387))

