[What is AES encryption and how does it work?](https://cybernews.com/resources/what-is-aes-encryption/)
[Video: AES Explained](https://www.youtube.com/watch?v=O4xNJsjtN6E)

[One Encryption Standard to Rule Them All!](https://www.youtube.com/watch?v=VYech-c5Dic)
## What is AES (Advanced Encryption Standard) Encryption?

In short, AES is a **symmetric** type of encryption, as it uses the same key to both encrypt and decrypt data.

It also uses the SPN (substitution permutation network) algorithm, applying multiple rounds to encrypt data. These encryption rounds are the reason behind the impenetrability of AES, as there are far too many rounds to break through.

There are three lengths of AES encryption keys. Each key length has a different number of possible key combinations:

- **128-bit key length: 3.4 x 1038**
- **192-bit key length: 6.2 x 1057**
- **256-bit key length: 1.1 x 1077**

Even though the key length of this encryption method varies, its block size - **128-bits (or 16 bytes)** - stays fixed. 

The variety of key lengths poses some questions. Why are there multiple key lengths? And, if the 256-bit key is the strongest of the bunch (even referred to as “military-grade” encryption), why don’t we just always use it?

Well, it all comes down to resources. For example, an app that uses AES-256 instead of AES-128 might drain your phone battery a bit faster.

Luckily, current technology makes the resource difference so minuscule that there is simply no reason not to use 256-bit AES encryption.

### The advantages of AES

Safety aside, AES encryption is very appealing to those who work with it. Why? Because the encryption process of AES is relatively easy to understand. This allows for **easy implementation**, as well as really **fast encryption and decryption times**.

In addition, AES requires less memory than many other types of encryption (like DES), which makes it a true winner when it comes to choosing your preferred encryption method.

Finally, when an action requires an extra layer of safety, you can combine AES with various security protocols like WPA2 or even other types of encryption like SSL. 

## Why do we use the AES algorithm?

Even if not exactly “ancient”, the advanced encryption standard is _old_.

Originally developed in 1998 by two Belgian cryptographers, Vincent Rijmen and Joan Daemen, AES has been around for more than 20 years. At first, it was referred to as **Rijndael** - a combination of the names of its developers.

Thanks to its impenetrability, AES encryption has already served as the **encryption standard** for 18 years. That’s because, in 2002, the National Institute of Standards and Technology (NIST) replaced the outdated Data Encryption Standard (DES) with AES. 

**Why did this happen?**

Well, first of all, the DES key length was a mere 56 bits. And it turned out that this isn’t nearly enough to keep encrypted information safe. For example, a test by **distributed.net** and the **Electronic Frontier Foundation** showed that DES can be easily cracked in a little bit more than 22 hours. Keep in mind that this was done in 1999, when computing power was far from what it is now.

Today, a powerful machine can crack a 56-bit DES key in 362 seconds. 

On the other hand, cracking a 128-bit AES encryption key can take up to 36 quadrillion years.

Just imagine what time it would take to crack a 256-bit AES key, which boasts a staggering number of 984,665,640,564,039,457,584,007,913,129,639,936 combinations. Keeping this number in mind, we can safely assume that a brute-force attack on AES encryption will not happen without a significant increase in computing power.

## Where is the AES algorithm used?

With its humble beginnings as the go-to encryption cipher of the US government, AES encryption quickly took the world by storm, becoming the **encryption standard** for basically anything we see online. As a result, you will have trouble finding industries or services that don’t use the AES algorithm.

Online banking credentials, passwords, and messages all need to be protected from people who can do harm. So, aside from “serving” the government (like the **National Security Agency**), the advanced encryption standard protects the sensitive data of a myriad of products.

### Examples of AES usage

Here are a few notable examples of where developers can use the AES encryption:

- **[VPNs (Virtual Private Networks)](https://cybernews.com/what-is-vpn/).** As the job of a VPN is to securely connect you to another server online, only the best methods of encryption can be considered so that your data wouldn’t leak. The VPNs that use the advanced encryption standard with 256-bit keys include [NordVPN](https://cybernews.com/best-vpn/nordvpn-review/), [Surfshark](https://cybernews.com/best-vpn/surfshark-vpn-review/), and [ExpressVPN](https://cybernews.com/best-vpn/expressvpn-review/).
- **Wi-Fi.** That’s right - wireless networks also use AES encryption (usually, together with WPA2). This is not the only type of encryption Wi-Fi networks can use, however, most of the other encryption methods are far less safe.
- **Mobile applications.** Many popular apps (like Snapchat and Facebook Messenger) use AES encryption in order to safely send info like photos and messages.
- **Archive and compression tools.** All major file compression programs use AES to prevent data from leaking. These tools include 7z, WinZip, and RAR.
- **OS system components.** Some operating system components (like file systems) use the advanced encryption standard for an extra layer of safety.
- **Programming language libraries.** The libraries of such coding languages like Java, Python, and C++ implement AES encryption.
- **[Password managers](https://cybernews.com/best-password-managers/).** These are the programs that carry _a lot_ of sensitive information. That’s why password managers like LastPass and Dashlane don’t skip the important step of AES implementation.

Even though this is an impressive list of what AES encryption is useful for, it still doesn’t include _everything_. 

Aside from all the things mentioned before, you will encounter the AES encryption algorithm in various **file systems** and **disk encryption systems**, as well as **web browsers**.

That’s right - you even used AES to open this article, as your browser must encrypt your connection with this page.

## How does AES encryption work?

Here’s what you should know from the get-go: without the proper background, the AES encryption algorithm can be a tough one to understand. To fully appreciate its intricacies, you would probably have to be a maths major (at least).

Luckily, it is possible to simplify the inner workings of the AES cipher. Replacing the binary code with “normal” symbols is one way of doing it.

In the following sections, I will briefly explain the main idea behind the cryptography of AES.

### 1. Dividing data into blocks

First, we have to keep in mind that AES is a **block cipher**. Unlike stream ciphers, it encrypts data in **blocks of bits** instead of bit-by-bit. 

Each of its blocks contains a column of 16 bytes in a layout of four-by-four. As one byte contains 8 bits, we get 128-bit block size (16x8=128).

Thus, the very first step of AES encryption is dividing the plaintext (text that is not written in code) into these blocks. 

So, let’s choose the text you want to encrypt. For example, it can be “better late than never”.

Applying the advanced encryption standard would turn the beginning of this phrase into the following block:

![AES encryption blocks](https://media.cybernews.com/2020/12/aes-encryption-blocks.png)

Note that this is only the first block of the text - the rest of the phrase would go into the next one.

### 2. Key expansion

This is an important step of AES encryption. It produces new 128-bit round keys with the help of [Rijndael’s key schedule](https://www.samiam.org/key-schedule.html).

Let’s say that our initial key is “extraterrestrial”:

![AES before key expansion](https://media.cybernews.com/2020/12/aes-encryption-before-key-expansion.png)

After applying Rijndael’s key schedule, the phrase will look like a jumble of random characters and might resemble something like this:

![AES encryption after key expansion](https://media.cybernews.com/2020/12/aes-encryption-after-key-expansion.png)

However, these characters won’t be so random after all, as Rijndael’s key schedule uses specific processes to encrypt each and every symbol.

The AES algorithm will need this set of new expanded keys a bit later.

### 3. Adding round key

This is the very first round of AES encryption. Here, the algorithm adds the initial key to our phrase, which was previously turned into a 4x4 block:

![AES key addition](https://media.cybernews.com/2020/12/aes-key-addition.png)

I know that adding two blocks of _text_ might seem impossible. However, remember that AES actually uses **binary code**, and what you now see is just a visual representation of what is actually happening in the binary language.

So, after adding the two blocks, we end up with a completely new block of cipher, which I will depict as this:

![AES key added](https://media.cybernews.com/2020/12/aes-encryption-key-added.png)

### 4. Byte substitution

Now, the AES algorithm substitutes every byte with a code according to a pre-established table called the **Rijndael S-box**. It looks like this:

![](https://media.cybernews.com/2020/12/AES-encryption-the-Rijndael-S-box.jpg)

According to the table, an element like 19 becomes d4, e9 becomes 1a, and so on. So, after the process of byte substitution, my block of cipher might take the appearance of something like this (keep in mind that it’s still a hypothetical representation of what the real deal looks like):

![AES encryption byte substitute](https://media.cybernews.com/2020/12/aes-encryption-byte-substitute.png)

As you can see, I marked a couple of columns with different colors. This will come in handy in the next step.

### 5. Shifting rows

In this step, the AES algorithm shifts the rows of the block it got during the byte substitution process.

The first row stays put. However, the second row gets shifted to the left by one byte, the third row moves to the left by two bytes, while the last one gets shifted by three bytes:

![AES encryption shifting rows](https://media.cybernews.com/2020/12/aes-encryption-shifting-rows.png)

### 6. Mixing columns

Talking in mathematical terms, this step multiplies each column by a predefined matrix, giving us a brand new block of code.

It is a really complicated process, involving a lot of advanced level mathematics.

For the sake of simplicity, let’s assume that I did the math and my new block now looks like this:

![AES encryption mix columns](https://media.cybernews.com/2020/12/aes-encryption-mix-columns.png)

### 7. Adding round key

It’s time to apply the round key we got in the _key expansion_ section. Let’s add it to the block we got in the previous section after the process of column mixing:

![AES encryption add round key](https://media.cybernews.com/2020/12/aes-encryption-add-round-key.png)

This action produces yet another block of binary code, which later on undergoes lots of further modifications.

### 8. Rinse and repeat

Now, the AES encryption algorithm will go through **many more rounds** of byte substitution, shifting rows, mixing columns, and adding a round key.

The number of **identical rounds** the data goes through depends on the AES key length:

- 128-bit key: 9 rounds
- 192-bit key: 11 rounds
- 256-bit key: 13 rounds

So, in the case of 256-bit key encryption, for example, the data goes through the previously mentioned steps 13 times in a row.

**However, that’s still not the end of it.**

There is one extra round after the mentioned 9, 11, or 13 rounds of encryption. During this additional round, the algorithm only goes through the stages of byte substitution, row shifts, and adding a round key. It leaves out the step of mixing columns.

Why? Because, at this point, that would be redundant. In other words, this action would use too much processing power without significantly altering the data.

So, **at the very end of the encryption process**, the data will have gone through the following number of rounds:

- **128-bit key: 10 rounds**
- **192-bit key: 12 rounds**
- **256-bit key: 14 rounds**

After all the rounds are completed, the original phrase “better late than never” will look like a set of random characters. 

## AES decryption

With the help of **inverse encryption**, the AES ciphertext can be restored to its initial state.

As mentioned before, the advanced encryption standard implements the method of **symmetric cryptography**. In other words, it uses the same key for both data encryption and decryption.

In this way, it differs from the algorithms that use asymmetric encryption, when both public and private keys are required.

So, in our case, AES decryption begins with the inverse round key. Afterwards, the algorithm reverses every single action (shift rows, byte substitution, and, later on, column mixing), until it deciphers the original message.

## Does AES encryption have any security issues?

Even though AES is an exceptionally secure type of encryption, it might not be 100% impenetrable a few years from now.

No known successful real-life attacks have been recorded so far, however, the rapid evolution of technology might pose potential threats in the future.

Also, mistakes happen. If someone implements AES encryption incorrectly, the potential errors might serve as a gateway for hackers.

Luckily, the **correct usage of AES prevents successful attacks from happening.**

To make sure that AES encryption is still impenetrable, cryptographers constantly work on ways to crack it, coming up with all kinds of theoretical attacks. Up until now, nobody managed to do it - only a few side-channel attacks were successful.

Below, I will share a few examples of how AES encryption can be compromised (at least in theory).

### Related-key attacks

Unlike brute-force attacks, related-key attacks target the encryption key itself. They require less time and effort, and have a higher chance of being successful.

This type of attack can work if the hacker knows (or suspects) the relationship between two different keys.

A few times, AES encryption has been a target of related-key attacks, the most notable one discovered in 2009. To prevent similar things from happening, cryptographers improved the complexity of the AES key schedule.

### Side-channel attacks

In case of improper implementation of a computer system, AES encryption is not completely immune to side-channel attacks.

This type of attack relies on data leakage, for example, electromagnetic leaks.

However, if AES is properly implemented, it can help detect the data leaks before anything bad happens.

### Known-key distinguishing attacks

In 2009, there was an attempt to crack AES-128 with the help of a known-key distinguishing attack.

It proved to be successful against the 8-round version of the 128-bit key length AES encryption. However, the actual AES-128 goes through 10 rounds of encryption, which means that the attack was not a threat in real life.

Also, to perform a known-key distinguishing attack, the hacker has to know the key, which is very unlikely.

### Key-recovery attacks

In 2011, a key-recovery attack was done as a test to crack AES.

This type of attack requires the hacker to have at least one pair of encrypted and decrypted messages.

However, the test didn’t provide significant results, as it only proved to be four times faster than a brute-force attack (which would still take billions of years).

## Conclusion

After reading this article, you might get the idea why AES encryption is referred to as the “gold standard” of encryption techniques.

Its speed, versatility, and immunity to all kinds of cyber attacks make it one of the most useful tools of today’s world.

And we are incredibly lucky it exists. 

## FAQ

Here you can find the answers to some of the most frequently asked questions about the AES cipher.

Want to know something but can’t seem to find the info you need? Drop your question in the comments and I’ll be there to help you.

### Is AES encryption secure?

**Yes.** A “brute-force” type of attack is virtually useless against the AES algorithm, as it would potentially take billions of years to crack it. However, if the encryption is implemented incorrectly, there might be some potential risks.  
  
Luckily, no hacker will be able to crack a correctly configured AES system. So, as long as there’s no error, your sensitive information is completely safe.

### Is AES the best encryption method?

There is no "best encryption method" because different situations call for different types of ciphers. However, AES is among the most secure symmetric encryption ciphers in the modern world.

### What is AES encryption used for?

As the industry standard for encryption, AES is used for all kinds of services to encrypt digital data.  
  
Virtual Private Networks, mobile application, password managers, wireless networks, and even video games use AES encryption.

### Which is better: RSA or AES?

RSA and AES are different types of encryption ciphers. Often, they are used in conjunction.