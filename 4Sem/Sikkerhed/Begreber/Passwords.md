# sadasd

> [!Link] 
> [Interessant hjemmeside](https://www.hivesystems.io/blog/are-your-passwords-in-the-green) med statistik på hashing udregninger pr sek, samt andet snak om sikkerhed

## Password styrke
![[Pasted image 20240215150510.png]]

## Cracking passwords

> [!Visualising the differences: Space vs Time]
>  A brute force attack takes a lot of time but that doesn't require a lot of storage. A rainbow table requires a lot of space, many tens or hundreds of GB, but it doesn't require a lot of time.

### 1. Brute-force or dictionary attack
- It means using automated software that systematically checks all possible passwords until the correct one is found.
- It’s trial-and-error process in which the hacker computes the hash of each word in a dictionary or a word list and then compares the resulting hash to the hash of the password.
### 2. Rainbow tables
- These are precomputed tables used for reversing cryptographic hash functions, usually used for cracking password hashes.
- The hacker has the hash of the password she wants to crack and searches for that hash in the list of precomputed hashes of the rainbow table.

### Cracking Passwords Countermeasures

in essence, make it as much a nuisance as possible. If you're more difficult to hack than the next mark, then it won't be worth it. They go for easy marks, since many people dont use strong passwords, or commit some other security faux-pas.
- Use **strong passwords** that consist of at least 12 random characters including both lower and uppercase letters, digits and special characters.
- **Do not use dictionary words** including combinations of these words no matter the language.
- **Do not store passwords unencrypted** like for example in word files. Do not write them down!
- **Do not reuse your passwords**! Use a unique password for each website or service
- Additionally, **setup 2-way authentication** for important websites like your bank, paypal or even Google or Facebook accounts
## Hands-on and examples in Linux:
### /etc/passwd vs /etc/shadow: both Can be used to crack the password.
#### **/etc/passwd**: all valid user accounts
![[Pasted image 20240215151105.png]]
#### **/etc/shadow**: requires ***root privileges*** to read and write the file
![[Pasted image 20240215151149.png]]
### [[John the Ripper (JTR)]]
