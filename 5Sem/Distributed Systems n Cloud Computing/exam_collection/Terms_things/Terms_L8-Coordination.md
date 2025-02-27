# Some Shit
ssssss


# Exam Questions
## Clock synchronization, [[Leader Election]]

### 1. Why is clock synchronization important in distributed systems?
It pertains to general coordination etc. For physical clocks. if a client asks the server, when is X available? and they dont have similar times ... shit!

for logical clocks.... whooo boy.
### 2. What is the main difference between physical clocks and [[Logical Clocks]]?
Logical clocks, reason their way to correct time keeping (in respects to when something happened) that reason being in relation to other events. see it as a list where events are added.

normal clocks keep the time, allowing for events to be described in their relation to that time
### 3. What is the purpose of [[Lamports Logical Clocks]]?

### 4. How do [[Vector Clocks]] improve upon [[Lamports Logical Clocks]]?

### 5. What problem do [[Mutual Exclusion]] algorithms solve in distributed systems?
To avoid threads or nodes from either accessing and manipulating the same data concurrently, or ensure an operation isn't halted/paused at a critical junction. Also just allows us to control access to things

### 6. Why do we need [[Leader Election]] in a distributed system?

### 7. How does the centralized [[Mutual Exclusion]] algorithm work?
Simple, really. theres a leader/coordinator. He keeps track of the state of a critical resource. So P1 wants to access the thing, asks leader if he can grab the lock. gets go ahead. meanwhile P2 has got the same idea, but the leader ignores their ass. P1 goes back and says theyre done, so leader allows P2 to take lock.
It's like a library and lending books. You ask for the book. they call you when it's back.
### 8. What is the main idea behind token-based [[Mutual Exclusion]] algorithms?
Equality. with the other one, a few processes could hog most of the access. Here the token gets passed (through some mechanism, perhaps a ring). Whoever has the token can use it to enter critical region, or pass it along. and on and on it goes/
### 9. Why might logical ordering of events sometimes be preferred over absolute time synchronization?
Time synch can be imprecise, but thats probably not the main reason. Why event synch in regards to time if it isn't needed? if the most important thing is that correct order of events is kept, then make that the metric.
### 10. How does Cristians algorithm synchronize clocks, and what are its limitations?

### 11. What is the principle behind Berkeleys algorithm for time synchronization?

### 12. How does the happened-before relation contribute to understanding event ordering in distributed systems?
That's the whole logic part of the logic clocks... [[Happened before principle]] the whole reason that you can say a happened before c, is that a happened before b and b before c.
say a happened before b. and process 2 received b before d, then it knows for a fact, that a happened before d. It allows us to build up interconnections and use logic to build out the chronology
### 13. Why can [[Lamports Logical Clocks]] fail to detect certain concurrency scenarios that [[Vector Clocks]] can?

### 14. How does the bully algorithm elect a coordinator in a distributed system?
Alright, so get this... Bullying is good. Process x figures out they need an election, and notifies all nodes of higher standing (read id). if none respond hey, x is new leader. else they respond. x+1 notifies x+2 ... and so on, until the top is reached. then the leader says to every, there's a new sheriff in town.
### 15. In the ring-based election algorithm, how is the new coordinator chosen among multiple processes?

### 16. What improvements does [[Network Time Protocol (NTP)|NTP]] introduce over simpler clock synchronization algorithms like [[Cristians Algorithm|Cristians]] or [[Berkeley Algorithm|Berkeleys]]
Different modes...
But there's a hierarchy. at the top the most precise reading of atomic clocks. who then propagate it downwards through layers. Spreads the communication needed wide, so that every node isn't constantly asking the turbo-experts for the time. Delegate, yknow? divide and conquer.
### 17. How do proof-of-work or proof-of-stake methods relate to [[Leader Election]] in large-scale distributed systems like blockchain networks?