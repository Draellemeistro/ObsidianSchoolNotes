
![[image_Space and Time Coupling.png]]
#### [[Space Coupling]]
##### [[Time Coupling]]
###### Properties:
- Communication directed towards a given receiver or receivers
- Receiver(s) must exist at that moment in time
- e.g., _synchronous communication ([[Request-Reply]], [[remote invocation]]_)
##### [[Time Uncoupling]]
###### Properties:
- Communication directed towards a given receiver(s)
- sender(s) and receiver(s) can have independant lifetimes
- e.g., _[[asynchronous communication]] (email, text messaging)_


----

#### [[Space Uncoupling]]
##### [[Time Coupling]]
###### Properties:
- Sender does not need to know the identity of receiver(s)
- Receiver(s) must exist at that moment in time
- e.g., _[[IP Multicast]]_ 
##### [[Time Uncoupling]]
###### Properties:
- Sender does not need to know the identity of receiver(s)
- sender(s) and receiver(s) can have independant lifetimes
- e.g., _[[indirect communication]] ([[Publish-Subscribe]])_