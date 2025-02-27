In [[k-fault tolerance]]
When a group can mask any k concurrent member failures (**k is called [[degree of fault tolerance]]**)

> [!warning] By using **2k + 1** servers, we can establish [[k-fault tolerance]]. However, we need a total of **3k + 1** servers if it is needed to deal with arbitrary failures.

# How large must a _k-fault-tolerant_ group be:
- with [[Halting Failures]] (crash / omission / timing failures) we need **k+1**
	- No member will produce an incorrect result, so the result of one member is good enough.
- With [[arbitrary failure]] we need **2k+1** members
	- The correct result can be obtained only through a majority vote.

### [[grouping operations]] and [[Failure Masking]]
##### IMPORTANT
- all members are identical
- all members process commands in the same order
##### Result
- only then do we know that all processes are programmed to do exactly the same thing.
###### OBSERVATION
the processes need to have [[Consensus]] on which command to execute next. 
...on to [[Flood-based consensus algorithm]]