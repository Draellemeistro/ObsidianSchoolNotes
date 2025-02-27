# Principles of Network Applications
## THE CLIENT-SERVER PARADIGM.
Which of the characteristics below are associated with a client-server approach to structuring network applications (as opposed to a P2P approach)?
- ==There is a server with a well known server IP address.==
- There is _not_ a server that is always on.
- ==There is a server that is always on.==
- ==HTTP uses this application structure.
- A process requests service from those it contacts and will provide service to processes that contact it.

## THE PEER-TO-PEER (P2P) PARADIGM.
  
Which of the characteristics below are associated with a P2P approach to structuring network applications (as opposed to a client-server approach)?
- HTTP uses this application structure.
- ==A process requests service from those it contacts and will provide service to processes that contact it.==
- ==There is _not_ a server that is always on.==
- There is a server that is always on.
- There is a server with a well known server IP address.


## UDP SERVICE
When an application uses a UDP socket, what transport services are provided to the application by UDP? Check all that apply.
- _Flow Control._ The provided service will ensure that the sender does not send so fast as to overflow receiver buffers.
- _Real-time delivery._ The service will guarantee that data will be delivered to the receiver within a specified time bound.
- _Congestion control._  The service will control senders so that the senders do not collectively send more data than links in the network can handle.
- _Loss-free data transfer._ The service will reliably transfer all data to the receiver, recovering from packets dropped in the network due to router buffer overflow.
- _Throughput guarantee_. The socket can be configured to provide a minimum throughput guarantee between sender and receiver.
- ==_Best effort service._  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.==


## TCP SERVICE.
When an application uses a TCP socket, what transport services are provided to the application by TCP?  Check all that apply.

- ==_Congestion control._  The service will control senders so that the senders do not collectively send more data than links in the network can handle.==
- _Throughput guarantee._ The socket can be configured to provide a minimum throughput guarantee between sender and receiver.
- ==_Loss-free data transfer._ The service will reliably transfer all data to the receiver, recovering from packets dropped in the network due to router buffer overflow.==
- _Best effort service._  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.
- _Real-time delivery._ The service will guarantee that data will be delivered to the receiver within a specified time bound.
- ==_Flow Control._ The provided service will ensure that the sender does not send so fast as to overflow receiver buffers==



# The web and HTTP
## “HTTP IS STATELESS.” 

What do we mean when we say “HTTP is stateless”? In answering this question, assume that cookies are not used.  Check all answers that apply.  

- ==An HTTP _server_ does not remember anything about what happened during earlier steps in interacting with this HTTP client.==
- We say this when an HTTP server is not operational.
- An HTTP client does not remember the identities of the servers with which  it has interacted.
- The HTTP protocol is not licensed in any country.
- An HTTP _client_ does not remember anything about what happened during earlier steps in interacting with any HTTP server.

## HTTP COOKIES. 
What is an HTTP cookie used for?


- A cookie is a code used by a client to authenticate a person’s identity to an HTTP server.
- ==A cookie is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this Web _browser_. \[Think about the distinction between a _browser_ and a _person_.]==
- Like dessert, cookies are used at the end of a transaction, to indicate the end of the transaction.
- A cookies is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this _person._ \[Think about the distinction between a _browser_ and a _person_.]
- A cookie is used to spoof client identity to an HTTP server.

## THE HTTP GET.

  What is the purpose of the HTTP GET message?

- The HTTP GET request message is sent by a web server to a web client to get the identity of the web client.
- ==The HTTP GET request message is used by a web client to request a web server to send the requested object from the server to the client.==
- The HTTP GET request message is sent by a web server to a web client to get the next request from the web client.
- The HTTP GET request message is used by a web client to post an object on a web server.

## CONDITIONAL HTTP GET. 
What is the purpose of the conditional HTTP GET request message?

- To allow a server to only send the requested object to the client if the client has never requested that object before.
- To allow a server to only send the requested object to the client if the server is not overloaded.
- ==To allow a server to only send the requested object to the client if this object has changed since the server last sent this object to the client==.
- To allow a server to only send the requested object to the client if the client is authorized to received that object.
## A detailed LOOK AT AN HTTP GET
![[Pasted image 20240527123150.png]]
## WHY WEB CACHING?

Which of the following are advantages of using a web cache? Sselect one or more answers.

- Caching allows an origin server to more carefully track which clients are requesting and receiving which web objects.
- ==Caching uses less bandwidth coming into an institutional network where the client is located, if the cache is also located in that institutional network.==
- Overall, caching requires  fewer  devices/hosts to satisfy a web request, thus saving on server/cache costs.
- ==Caching generally provides for a faster page load time at the client, if  the web cache is in the client’s institutional network, because the page is loaded from the nearby cache rather than from the distant server.==


## HTTP/2 VERSUS HTTP/1.1.
  Which of the following are changes between HTTP 1.1 and HTTP/2? Note: select one or more answers.

- ==HTTP/2 allows a large object to be broken down into smaller pieces, and the transmission of those pieces to be interleaved with transmission  other smaller objects, thus preventing a large object from forcing many smaller objects to wait their turn for transmission.==
- HTTP/2 has many new HTTP methods and status codes.
- HTTP/2 provides enhanced security by using transport layer security (TLS).
- ==HTTP/2 allows objects in a persistent connection to be sent in a client-specified priority order.==

## WHAT'S IN AN HTTP REPLY?

Which of the following pieces of information will appear in a server’s application-level HTTP reply message? (Check all that apply.)
 

- The server's IP address
- A checksum
- ==A response code==
- The name of the Web server (e.g., gaia.cs.umass.edu)
- ==A response phrase associated with a response code==
- A sequence number

## IF-MODIFIED-SINCE.

What is the purpose of the _If-Modified-Since_ field in a HTTP GET request message

- To inform the HTTP cache that it (the cache) should retrieve the full object from the server, and then cache it until the specified time.
- To allow the server to indicate to the client that it (the client) should cache this object.
- ==To indicate to the server that the client has cached this object from a previous GET, and the time it was cached.==
- To indicate to the server that the server should replace this named object with the new version of the object attached to the GET, if the object has not been modified since the specified time
- To indicate to the server that the client wishes to receive this object, and the time until which it will cache the returned object in the browser's cache.

## COOKIES.

What is the purpose of a cookie value in the HTTP GET request?

- The cookie value encodes the format of the reply preferred by the client in the response to this GET request.
- The cookie value is an encoding of a user email address associated with the GET request.
- ==The cookie value itself doesn't mean anything.  It is just a value that was returned by a web server to this client during an earlier interaction.==
- The cookie value indicates whether the user wants to use HTTP/1, HTTP/1.1, or HTTP/2 for this GET request.
- The cookie value encodes a default set of preferences that the user has previously specified for this web site.

## WHAT HAPPENS AFTER AN HTTP REPLY?

Suppose an HTTP server sends the following HTTP response message a client:  
  
HTTP/1.0 200 OK  
Date: Wed, 09 Sep 2020 23:46:21 +0000  
Server: Apache/2.2.3 (CentOS)  
Last-Modified: Wed, 09 Sep 2020 23:51:41 +0000  
ETag:17dc6-a5c-bf716880.  
Content-Length: 418  
Connection: Close  
Content-type: image/html  
  
**Will the web server close the TCP connection after sending this message?**

- There’s not enough information to answer this question.
- ==Yes, because this is HTTP 1.0==
- No, this is a persistent connection, and so the server will keep the TCP connection open.

# E-MAIL
## E-MAIL DELAYS.

How many RTTs are there from when a client first contacts an email server (by initiating a TCP session) to when the client can begin sending the email message itself – that is following all initial TCP or SMTP handshaking required?

  

- 2.5
- 1
- ==3==
- 0
- 2

## COMPARING AND CONTRASTING HTTP AND SMTP.

Which of the following characteristics apply to HTTP only (and do _not_ apply to SMTP)?  Note: check one or more of the characteristics below.

- Uses a blank line (CRLF) to indicate end of request header.
- Is able to use a persistent TCP connection to transfer multiple objects.
- Operates mostly as a “client pull” protocol.
- Uses CRLF.CRLF to indicate end of message.
- Operates mostly as a “client push” protocol.
- Uses server port 80.
- Has ASCII command/response interaction, status codes.
- Uses server port 25.

## COMPARING AND CONTRASTING HTTP AND SMTP (2).

Which of the following characteristics apply to SMTP only (and do _not_ apply to HTTP)?  Note: check one or more of the characteristics below.

- Is able to use a persistent TCP connection to transfer multiple objects.
- Has ASCII command/response interaction, status codes.
- Uses server port 25.
- Operates mostly as a “client push” protocol.
- Uses CRLF.CRLF to indicate end of message.
- Operates mostly as a “client pull” protocol.
- Uses a blank line (CRLF) to indicate end of request header.
- Uses server port 80.

## COMPARING AND CONTRASTING HTTP AND SMTP (3).

Which of the following characteristics apply to both HTTP and SMTP? Note: check one or more of the characteristics below.

- Is able to use a persistent TCP connection to transfer multiple objects.
- Uses a blank line (CRLF) to indicate end of request header.
- Has ASCII command/response interaction, status codes.
- Uses CRLF.CRLF to indicate end of message.
- Operates mostly as a “client push” protocol.
- Operates mostly as a “client pull” protocol.

## WHICH E-MAIL PROTOCOL?

  
  

  Match the functionality of a protocol with the name of a the email protocol (if any) that implements that functionality.
 ##### QUESTION LIST:

- Pushes email from a mail client to a mail server.
==SMTP==

- Pulls mail from one mail server to another mail server.
==Neither SMTP nor IMAP does this.==

- Pulls email to a mail client from a mail server.
==IMAP==



## Domain Name Service