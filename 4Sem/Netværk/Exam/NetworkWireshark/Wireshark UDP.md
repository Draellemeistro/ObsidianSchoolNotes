# Opgave Dokument
![[Wireshark_UDP_v8.0.pdf]]


# Opgave svar
## 1 
==**Source port** : 4334
**Destination port** : 161==
Length : 58
Checksum : 0x65f8
![[Pasted image 20240526185940.png]]

## 2
By consulting the displayed information in Wireshark’s packet content field for this packet, determine the length (in bytes) of each of the UDP header fields
**==2 bytes per field==**

## 3
he value in the Length field is the length of what? (You can consult the text for this answer). Verify your claim with your captured UDP packet
==**How many bytes the message is, including header fields**: 
payload = 50
dest port = 2
src port = 2
checksum = 2
length header = 2
50 + 2 + 2 + 2 + 2 = 58==

## 4
What is the maximum number of bytes that can be included in a UDP payload? (Hint: the answer to this question can be determined by your answer to 2. above
The length field use 2 bytes to display length. 
2Bytes = 16bits. 16^2 = 1024  2^6 = 1024 * 32 * 2 = 65 536
minus 1
==65 507 bytes payload maximum==

## 5 
What is the largest possible source port number? (Hint: see the hint in 4.
==16 bits which means port number can be between **0 and 65,535**==

## 6
What is the protocol number for UDP? Give your answer in both hexadecimal and decimal notation. To answer this question, you’ll need to look into the Protocol field of the IP datagram containing this UDP segment (see Figure 4.13 in the text, and the discussion of IP header fields).
1 byte to show it. 
**==11 for hex, 17 decimal==**

## 7
Examine a pair of UDP packets in which your host sends the first UDP packet and the second UDP packet is a reply to this first UDP packet. (Hint: for a second packet to be sent in response to a first packet, the sender of the first packet should be the destination of the second packet). Describe the relationship between the port numbers in the two packets
==The ports are the links between hosts. send to port 123, response comes from 123. receive from 456, also send from 456.==