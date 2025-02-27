# What is it?
sss


# More info
## Modes
### 1. Single crack mode
uses the login names together with other fields from the passwd file, also with a large set of mangling rules applied. This is the fastest cracking mode and is applicable to very simple passwords.
### 2. Dictionary attack
In this mode you need to supply a dictionary file that contains one word per line and a password file. You can enable word mangling rules which are used to modify or "mangle" words producing other likely passwords.
### 3. "Incremental" mode
This is the most powerful cracking mode because it will try all possible character combinations as passwords. If you supply a random password with length of more than 12-14 chars will never terminate and you'll have to interrupt it manually

## brute force offline
- JtR operates mainly on hashed passwords stored in files on your local system.
- is already installed in Kali Linux

- 
- 
- 
## How-to
### 1. Single crack mode
1. The first step is to combine the provided password and shadow files into a single file.
	1. **unshadow /etc/passwd /etc/shadow > unshadowed.txt**
2. Check the content of the combined file
	1. **cat unshadowed.txt**
3. Run John
	1. **john -single --forma=crypt unshadowed.txt**
4. Run John
	1. **john –show unshadowed.txt**
### 2. Dictionary attack
1. John the Ripper comes with its own password list in:
	1.  **/usr/share/john**
2. On Kali Linux there are more dictionary files in:
	1.  **/usr/share/metasploit-framework/data/wordlists**
3. The first step is to combine the provided password and shadow files into a single file. 
	1. **john --wordlist=/usr/share/john/password.lst --rules --forma=crypt unshadowed.txt**
4. Run John
	1. **john –show unshadowed.txt**
### 3. "Incremental" mode
#TODO 

## Other Tools for Brute-force attacks or dictionary attacks
- **Automated tools:** [[Hydra]], [[Medusa]]
	- Primarily targets online services like SSH, FTP, HTTP, and more.
	- But we need to know the username (or try to guess it)
	- And then we have to choose a password list - and we choose the John The Ripper list.
	- **Example**:
		-  Hydra -l admin -P /usr/share/john/password.lst -vV ftplogin.com ftp