
> [!NOTE] Title
> between mail servers to send email messages. **client** sending mail server. **"server"** receiving mail server


> [!NOTE] Observations
> **Comparisons with [[Netværk/Begreber/Application-layer/HTTP]]**:
> - Both have ASCI command/response interaction, status codes
> - **HTTP**: client pull **SMTP**: client push
> - **HTTP**: Each object encapsulated in its own response message  **SMTP**: Multiple objects sent in multipart message
> - **SMTP** uses persistent connection
> - **SMTP** requires message(header and body) to be in 7-bit ASCII
> - **SMTP** server uses CRLF.CRLF to determine end of message


![[Pasted image 20240527065238.png]]
# See also


# More info
## SMTP RFC (5321)
- uses [[TCP service]] to reliably transfer email message from client (the mail server initating connection) to server, **==port 25 (why??)==**
	- **Direct Transfer**: Sending server (acting like client) to receiving server
- **==Three phases of tranfser==**
	- SMTP handshaking (greeting)
	- SMTP Transfer of message
	- SMTP closure
- Command/response interaction (like [[Netværk/Begreber/Application-layer/HTTP]])
	- **Commands**: ASCII text
	- **Response**: Status code and phrase
	- ==sample SMTP interaction== *S: 220 hamburger.edu*
![[Pasted image 20240527065625.png]]
### Scenario / Example
![[Pasted image 20240527065654.png]]
## Observations
