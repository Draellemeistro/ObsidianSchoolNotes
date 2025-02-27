
# Krypteret chat
## Lignende produkter
- [[Samlet Feature-list]]
	- [[Signal]]
	- [[Telegram]]
	- [[WhatsApp]]
	- [[Wickr Me]]
	- [[Wire - Secure messenger]]

- Signal
- Telegram
- WhatsApp
- Wickr Me
- Wire - Secure Messenger
### Cost Factors To Consider For Developing a Message Application
![[Pasted image 20240219111222.png]]

## Artikler
1.  [How to make a secure messaging app](https://www.amplework.com/blog/how-to-make-a-secure-messaging-app/)
2. [Developing a real-time secure chat application like WhatsApp & Signal with end-to-end encryption.](https://www.qed42.com/insights/developing-a-real-time-secure-chat-application-like-whatsapp-signal-with-end-to-end-encryption)
3. [Build an End-to-End Encrypted Chat with Seald and PubNub](https://www.pubnub.com/blog/build-an-end-to-end-encrypted-chat-with-seald-and-pubnub/)
4. [How encrypted messaging changed the way we protest](https://cybernews.com/news/how-encrypted-messaging-changed-the-way-we-protest/)
5. [What is AES encryption and how does it work?](https://cybernews.com/resources/what-is-aes-encryption/)
6. [Python chat](https://github.com/ludvigknutsmark/python-chat)
7. [A Cryptographer's Guide to End-to-End Encryption](https://hackernoon.com/a-cryptographers-guide-to-end-to-end-encryption?ref=hackernoon.com)
8. [60 Stories To Learn About Compliance](https://hackernoon.com/60-stories-to-learn-about-compliance?ref=hackernoon.com)

### 1) [How to make a secure messaging app](https://www.amplework.com/blog/how-to-make-a-secure-messaging-app/)
#### Snak om [[Signal]]
*Currently, some popular messaging apps like – “**Signal**, **WhatsApp** and **Telegram**” offer [[end-to-end encryption projekt |end-to-end encryption]] as a standard feature.*
[[Signal|Signal App]] also uses the Signal Protocol, the protocol uses a combination of advanced cryptographic techniques – including [[Extended Triple Diffie-Hellman|Diffie-Hellman]] key exchange and [[AES|AES encryption]].

Secure messaging also comes with a feature of [[self-destructing messages]]

[[Password protection]] allows users to lock their messaging app with a password, adding an extra layer of security. To ensure the security of your messaging app, it’s essential to verify your contacts to ensure you’re communicating with the right person.

#### Steps To Create A Secure Messaging App Like “Signal”
==Step 1==: Define the purpose and features of your application
==Step 2==: Design the app architecture: deciding on the platform, programming language, and [framework](https://www.amplework.com/blog/top-9-backend-frameworks-for-web-app-development/)
==Step 3==: Implement end-to-end encryption
==Step 4==: Adding [[Security Features]]
	- **Disappearing messages –** this feature allows users to set a time limit on how long their messages can be visible before they disappear.
	- **Self-destructing messages –** similar to disappearing messages, self-destructing messages can be set to automatically delete themselves after they have been viewed.
	- **Anonymous chat –** this feature allows users to chat anonymously without revealing their identity to other users.
	- **Voice and video calls –** by adding voice and [video calling](https://www.amplework.com/blog/15-best-free-video-calling-apps/) features to your secure messaging app, you can provide a complete communication solution for your users.
	- **Group chat management –** a well-designed group chat management feature can help users manage and organize their group chats effectively
==Step 5==: Conduct security testing: ex conducting[[ penetration testing]], [[code reviews]], and [[security audits]].
==Step 6==: Launch the application & maintain it



### 2) [Developing a real-time secure chat application like WhatsApp & Signal with end-to-end encryption.](https://www.qed42.com/insights/developing-a-real-time-secure-chat-application-like-whatsapp-signal-with-end-to-end-encryption)
#### Technology Stack

**Client Application**
1. ReactJS for UI
2. Axios Library for handling AJAX calls
3. WebSocket library for real-time message exchange
4. Signal Protocol for end-to-end encryption
5. Tailwind CSS

**Server Application**
1. NodeJS
2. Express
3. Mongoose for MongoDB integration
4. TypeScript as the server-side language
5. REST APIs
#### Making it real-time
ith the traditional request-response model, we have few options:
1. **Refresh Webpage**
2. **HTTP protocol**
3. **HTTP 1.1 Keep-Alive Protocol**
4. **Short Polling**
5. **Long Polling**
6. **Server-Sent Events**
4, 5, 6: [Polling vs SSE vs WebSocket— How to choose the right one](https://codeburst.io/polling-vs-sse-vs-websocket-how-to-choose-the-right-one-1859e4e13bd9)
1(?), 2, 3: [HTTP Request/Response Cycle](https://backend.turing.edu/module2/lessons/how_the_web_works_http#:~:text=The%20Request%20and%20Response%20Cycle&text=When%20the%20server%20receives%20that,be%20rendered%20to%20the%20user.) og [Building Real-Time Applications with WebSockets](https://frontend.turing.edu/lessons/module-4/websockets.html)



### 3) [Build an End-to-End Encrypted Chat with Seald and PubNub](https://www.pubnub.com/blog/build-an-end-to-end-encrypted-chat-with-seald-and-pubnub/)

[Eksempel projekt på Github](https://github.com/seald/pubnub-example-project?ref=hackernoon.com)

**This article has been contributed by a third party,** [**seald**](https://www.seald.io/)**, and presents an alternative to PubNub's built-in** [**message-level encryption**](https://www.pubnub.com/docs/general/setup/data-security#message-encryption)**. It was originally published on** [**Hackernoon**](https://hackernoon.com/how-to-build-an-end-to-end-encrypted-chat-with-seald-and-pubnub)**.**

#### Pubnub
PubNub is a real-time communication service that can be integrated into most applications. Reliable and scalable, it can easily be integrated with the most common frameworks.

#### Seald SDK
Seald.io offers an SDK that allows you to carry out **end-to-end encryption**, with advanced management features, **without any prior cryptographic knowledge.** This SDK can be integrated into web, backend, mobile, or desktop applications.

#### Why E2EE? (End-to-end encryption)

> [!NOTE] #### Why E2EE? ([[end-to-end encryption projekt |end-to-end encryption]])
> End-to-end encryption allows you **to keep control at all times,** when your data is in transit, when it is at rest, and even when it is not in your hand. Thus, it offers far wider protection than other encryption technologies (TLS, full-disk encryption, ...).
> 
> Whenever you face a case where [**compliance**](https://hackernoon.com/60-stories-to-learn-about-compliance?ref=hackernoon.com) **is important** (GDPR, HIPAA, SOC-2,...) or where you have **sensitive data** (medical, defense,...), end-to-end encryption is a must-have.

==Vulnerabilities rarely come from the encryption itself, but most often **from keys being leaked** through flaws in the security model.==
Using a third-party service for your security allows you **to not have a single point of failure.** Seald.io proposes a robust security model, **certified by the ANSSI,** with real-time access-management control, user revocation and recovery, 2FA, and more.







### 4) [How encrypted messaging changed the way we protest](https://cybernews.com/news/how-encrypted-messaging-changed-the-way-we-protest/)
#### Secure communications
**Signal is the messaging service of choice for those in the cybersecurity field**, with the app using its own protocol to provide robust and reliable end-to-end encryption for voice, video, and instant messages. It’s no surprise, therefore, that the number of downloads of the app has soared over the summer, with **==an estimated 51,000 downloads in the week after George Floyd’s death on the 25th of May. This then grew to 78,000 new downloads as the protests began to spread nationwide.==**

> [!NOTE] Signal's technology 
> Signal's technology is based upon the [[AES]], [[Extended Triple Diffie-Hellman]], [[Double Ratchet]], and [[Sesame protocols]] to make it arguably the most secure messaging app on the market. This is reinforced by the open-source nature of the technology rendering it a constant source of testing by the cybersecurity community.


#### Coordinating activity
With platforms such as Signal, the focus is more on the coordination of activity and the recruitment of participants via word-of-mouth. The adoption of the technology has blossomed as awareness of the various tactics used by the police to monitor citizens during protests.
**==The end-to-end encryption deployed by Signal makes it impossible for law enforcement agencies to monitor what is being said, as it is literally only readable by the sender and the recipient.==**

> [!NOTE] snooping is possible doesn’t mean that it’s happening.
> But the fact that it’s possible, and that there is a clear incentive for government agencies to do so during mass protests renders it a risk many protestors are clearly preferring not to take.

SMS messages are not encrypted at all, so can be easily read, while **WhatsApp’s encryption is only as secure as Facebook,** **==and with moves being made to force tech companies to provide access to data, it remains to be seen how strong the company’s resolve remains for what is a free service.==**

**By contrast, Signal has already proven its chops in this regard, as they stood up against a legal request for data back in 2016.** The fact that none of the data exchanged when we communicate via the platform is stored on company servers means nothing remains to be accessed by the government.
#### The changing nature of protest
For many years, experts in the domain have advised people to make sure they attend protests in as non-descript clothing as possible so that they can’t be easily identified in any footage from the protest. **==Signal has new tool that allows for photos to be blurred to limit the ability of governments to identify people from their photos.==**

There is a growing awareness of our personal responsibility to ensure that the way we behave online is conducive to the values we hold. developers are striving to keep our data and our communication private, so too are government agencies working to allow law enforcement officers access when required.

> [!NOTE] [Lawful Access to Encrypted Data Act](https://www.judiciary.senate.gov/imo/media/doc/S.4051%20Lawful%20Access%20to%20Encrypted%20Data%20Act.pdf)
> force technology companies operating in the US to give the government and law enforcement agencies access to encrypted data when asked to do so, and this is but one of a number of initiatives that threaten our privacy online.



### 5) [What is AES encryption and how does it work?](https://cybernews.com/resources/what-is-aes-encryption/)
**AES encryption**, or **advanced encryption standard**, is a type of cipher that protects the transfer of data online.

Currently, **==AES is one of the best encryption protocols available==**, as it flawlessly combines speed and security, letting us enjoy our daily online activities without any disruption. no surprise that AES **has become the industry standard for encryption.**

#### What is AES (Advanced Encryption Standard) Encryption?
[[AES]] is a **==symmetric==** **type of encryption, as it uses the same key to both encrypt and decrypt data.**

t also uses the **==SPN (substitution permutation network) algorithm==**, applying multiple rounds to encrypt data. These encryption rounds are the reason behind the impenetrability of AES, as there are far too many rounds to break through.


> [!NOTE] AES encryption keys
> There are three lengths. Each key length has a different number of possible key combinations:
> - **128-bit key length: 3.4 x $10^{38}$**
>  - **192-bit key length: 6.2 x $10^{57}$**
>  - **256-bit key length: 1.1 x $10^{77}$**
>
>Even though the key length of this encryption method varies, its block size - **128-bits (or 16 bytes)** - stays fixed.

##### Why are there multiple key lengths?
And, if the 256-bit key is the strongest of the bunch (even referred to as “military-grade” encryption), why don’t we just always use it?
it all comes down to resources. For example, an app that uses AES-256 instead of AES-128 might drain your phone battery a bit faster.

Luckily, current technology makes the resource difference so minuscule that there is simply no reason not to use 256-bit AES encryption.




### 6) [Python chat](https://github.com/ludvigknutsmark/python-chat)
#### Introduction
A basic example of a chat application which supports groups up to 10 people for each room. **==The goals of this project was to gain knowledge and experience in implementing encryption, diffie-hellman key exchange, digital signatures and SSL certificates into an Python application.==** This application is NOT(!!!!) meant for production or the sending of any sensitive data, therefore the GUI is ugly and very simplified and ==some huge security details are overlooked==, **see security issues for details.**

##### Some security features/measures is:
- End-to-end encrypted message between clients using **==Fernet==**, which is **a method that builds upon AES-128-CBC mode and a SHA256 hash authentication code (HMAC)**.
- **==[[Elliptic Curve Diffie-Hellman]] (ECDH) key exchange.==** I've implemented ECDH so that it works for more than two clients. Further explaination below.
- **SSL socket** between clients and server, where server acts as both server and CA.
- **Digital signatures using elliptical curves**.
#### [[Elliptic Curve Diffie-Hellman]] (ECDH)
The client that creates the chatroom is elected "key hub". The key hub is responsible for creating a Fernet key which will be used by all parties. Each client that now connects to the chat room does a key exchange with the key hub using elliptic curve diffie-hellman to negotiate a shared key. The shared key is then used by the hub to encrypt the Fernet key by using AES-CBC mode. The client then decrypts the Fernet key by using the shared key. Both parties now shares the same Fernet key and can exchange messages without any interception.

If the key hub exits the chat a new hub is elected, and no further action is needed as the new key hub already has the Fernet key.

#### Security issues
Those that I know of:
- When a server verifies a client the client first sends it public key to the server. This is obviously wrong. A solution would be a login/register for clients which would generate a public key put in a database that the server would check with each challenge.
- The SSL certificate verification from the client has a callback function that is not implemented. Further research is essential for this to be OK.





### 7) [A Cryptographer's Guide to End-to-End Encryption](https://hackernoon.com/a-cryptographers-guide-to-end-to-end-encryption?ref=hackernoon.com)
#TODO 

### 8) [60 Stories To Learn About Compliance](https://hackernoon.com/60-stories-to-learn-about-compliance?ref=hackernoon.com)
#TODO 

### 9) 