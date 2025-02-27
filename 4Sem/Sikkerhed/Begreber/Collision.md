- Two messages result in identical digests.
- Inevitable, it cannot be avoided
	- it is a byproduct of "fixed width digests"
# Definition
asdasd
asda
sd

## Why collision attacks matter
- replace legit file with malicious file
	- The malicious file's hash would match the expected hash, bypassing integrity checks.
- bypass authentication
	- An attacker could leverage a collision attack to craft a different input (password) that produces the same hash as a legitimate user's password.
- sign malware with a forged certificate
	- By creating a collision with a trusted certificate, they could trick systems into accepting the malware as legitimate.
- forge digital signature
	- Create a document with the same hash as a legitimate one, making it appear signed by the same person.
- flood systems with colliding data
	- Overwhelm systems with data that hashes to the same value, causing denial-of-service.

### MD5 Collision Attack: Generating Two Different Files with the Same Hash

> [!LINK] 
> Baseret på [HashClash](https://www.win.tue.nl/hashclash/)

We will generate two different files with **the same MD5 hash values**. We will use the **md5collgen** program
It takes as an input a prefix file with any arbitrary content and generates two output files, out1.bin and out2.bin.
	![[Pasted image 20240215154145.png]]
