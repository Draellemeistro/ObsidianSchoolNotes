
> [!NOTE] Three major components
> - User Agents
> - Mail Servers
> - [[SMTP]] Simple Mail Transger Protocol


# see also


# E-mail
![[Pasted image 20240527064914.png]]
## User Agent / "Mail Reader"
- Composing, Editing, Reading mail messages
- Outlook, iphone mail client etct
- Outgoing, incoming message stored on server
## Mail server
- **Mailbox** contains incoming messages for user
- **Message Queue** of outgoing, to be sent, mail messages
## SMTP protocol
- between mail servers to send email messages
- **client** sending mail server
- **"server"** receiving mail server
## [[Messages|message]] format
![[Pasted image 20240527070636.png]]

### Retrieving email: Mail Acces Protocols
![[Pasted image 20240527070749.png]]
- [[SMTP]]: Delivery/storage of e-mail messages to receiver's server
- **Mail Access Protocol**: retrieval from server
	- [[IMAP]]: Internet Mail Access Protocol ==RFC 3501==
		- Messages stored on server
		- IMAP provides retrieval, deletion, folders of stored messages on server
- [[Netværk/Begreber/Application-layer/HTTP]]: Gmail, Hotmail, Yahoo!Mail, etc. 
- provides web-based interface **==on top of==** 
	- **SMTP** to send.
	- **IMAP** or **POP** to retrieve e-mail messages