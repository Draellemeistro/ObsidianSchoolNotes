
## [[Redundancy]] for [[Failure Masking]]
## Types of redundancy
### [[Information-redundancy]]
Add extra bits to data units so that errors can be recovered when bits are garbled
### [[Time-redundancy]]
Design a system such that an action can be performed again if anything went wrong. Typically used when faults are transient or intermittent.
### [[Physical-redundancy]]
Add Equipment or processes in order to allow one or more components to fail. **This type is extensively used in [[Distributed Systems]]** (see [[Replication]])
## [[Process-groups|Groups]] and [[Failure Masking]]

> [!NOTE] [[k-fault tolerance]]
> When a group can mask any k concurrent member failures (**k is called [[degree of fault tolerance]]**)

### How large does a _k_-fault tolerant group need to be?
- with [[Halting Failures]] (crash/omission/timing failures): we need a total of $k+1$ members as **no member will produce an incorrect result, so the result of one member is good enough.**
- with [[arbitrary failure|arbitrary failures]]: **we need $2k+1$ members so that the correct result can be obtained through a majority vote.** 

> [!NOTE] Important assumptions
> - all members are identical
> - All members process commands in the same order
> **result:** we can now be sure that all processes do exactly the same thing.

