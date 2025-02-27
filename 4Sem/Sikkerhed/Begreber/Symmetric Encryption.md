Symmetric encryption uses the same key to both encrypt and decrypt data.
![[Pasted image 20240220135656.png]]
## Let’s try
### aes.py
```python
from Crypto.Cipher import AES

from Crypto.Util.Padding import pad, unpad

from Crypto.Random import get_random_bytes

import base64

  

def aes_encrypt(plaintext, key):

    # Ensure the key is of valid length (16, 24, 32 bytes)

    key = pad(key.encode(), 32)[:32]  # This pads the key to 32 bytes or cuts it to 32 bytes if it's longer

    # Generate a random 16-byte initialization vector    

    iv = get_random_bytes(16)

  

    # Create the AES cipher object with the key and CBC mode

    cipher = AES.new(key, AES.MODE_CBC, iv)

  

    # Pad the plaintext to be a multiple of AES block size

    padded_plaintext = pad(plaintext.encode(), AES.block_size)

  

    # Encrypt the padded plaintext

    ciphertext = cipher.encrypt(padded_plaintext)

  

    # Combine the IV and ciphertext into a single byte string for easy handling

    encrypted_data = iv + ciphertext

  

    # Return the encrypted data in base64 encoded form to ensure it's ASCII text

    return base64.b64encode(encrypted_data)

  

def aes_decrypt(encrypted_data, key):

    # Decode the encrypted data from base64

    encrypted_data = base64.b64decode(encrypted_data)

    # Ensure the key is of valid length (16, 24, 32 bytes)

    key = pad(key.encode(), 32)[:32]  # This pads the key to 32 bytes or cuts it to 32 bytes if it's longer

  

    # Extract the IV from the encrypted data

    iv = encrypted_data[:16]

  

    # Create the AES cipher object with the key and CBC mode

    cipher = AES.new(key, AES.MODE_CBC, iv)

  

    # Decrypt the ciphertext

    plaintext = unpad(cipher.decrypt(encrypted_data[16:]), AES.block_size)

  

    # Return the plaintext as a string

    return plaintext.decode()

  

# Ask user for input

plaintext = input("Enter the message you want to encrypt: ")

key = input("Enter a password (used as encryption key): ")

  

# Encrypt the plaintext

encrypted_data = aes_encrypt(plaintext, key)

print("Encrypted (base64 encoded): ", encrypted_data.decode())

  

# Optional: Decrypt the encrypted data to verify

# If needed, uncomment the following lines:

decrypted_data = aes_decrypt(encrypted_data, key)

print("Decrypted: ", decrypted_data)
```
### des.py
```python
import base64

from Crypto.Cipher import AES, DES

from Crypto.Util.Padding import pad

from Crypto.Random import get_random_bytes

  

def welcome_message():

    """Prints a welcome message and instructions."""

    print("Welcome to the Encryption Demo!")

    #print("Choose an encryption algorithm:")

def get_user_input():

    """Gets user input for message and encryption choice."""

    message = input("Enter your message to encrypt: ")

    while True:

        choice = input("Choose encryption (1 for DES, 2 for AES): ")

        if choice in ("1", "2"):

            return message, int(choice)

        else:

            print("Invalid choice. Please enter 1 or 2.")

  

def encrypt_message(message, choice):

    """Encrypts the message using DES or AES based on the user's choice."""

    if choice == 1:

        # DES encryption

        key = get_random_bytes(8)  # DES key is 8 bytes long

        cipher = DES.new(key, DES.MODE_ECB)

        padded_message = pad(message.encode(), DES.block_size)

        ciphertext = cipher.encrypt(padded_message)

    else:

        # AES encryption

        key = get_random_bytes(16)  # AES key is 16 bytes long (AES-128)

        cipher = AES.new(key, AES.MODE_CBC)

        padded_message = pad(message.encode(), AES.block_size)

        iv = cipher.iv  # Initialization vector for AES

        ciphertext = cipher.encrypt(padded_message)

        ciphertext = iv + ciphertext  # Prepend IV to ciphertext for AES

  

    # Encode ciphertext in Base64 for easier handling

    ciphertext_b64 = base64.b64encode(ciphertext).decode('utf-8')

  

    return ciphertext_b64

  

def main():

    """Main function that runs the entire demo."""

    welcome_message()

    message, choice = get_user_input()

    ciphertext = encrypt_message(message, choice)

    print("Encrypted message:", ciphertext)

  

if __name__ == "__main__":

    main()
```