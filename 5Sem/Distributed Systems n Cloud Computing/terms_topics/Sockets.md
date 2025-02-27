Sockets are rather low level and programming mistakes are easily made. However, the way that they are used is often the same (such as in client-server setting).

![[image_Sockets.png]]
### Operations
- `socket` - create a new communication endpoint
- `bind` - Attach a local address to a socket
- `listen` - Tell OS what the max number of pending connection requests should be
- `accept` - Block caller until a connection request arrives.
- `connect` - Actively attempt to establish a connection
- `send` - Send some data over the connection
- `receive` - receive some data over the connection
- `close` - Release the connection

### Maybe relevant
![[image_Sockets-1.png]]