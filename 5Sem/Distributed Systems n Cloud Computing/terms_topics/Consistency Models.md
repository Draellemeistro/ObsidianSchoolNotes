relating to [[Consistency]]
## What is it???
A contract between a (distributed) data store and processes, in which the data store specifies precisely what the results of read and write ops are in the presence of concurrency
##### WE CAN ACTUALLY TALK ABOUT A [[degree of consistency]]
also **INCONSISTENCIES CAN BE HANDLED AT DIFFERENT LEVELS**
#### Data store
a distributed collection of storages
![[image_Consistency Models 1.png]]
## Ideas and philosphy
### [[Happened before principle]]

> [!NOTE] **a -> b**
> - "a happens first, afterwards b happens"
> - "a happens before b"
> - "a might cause b"

# Data-Centric Consistency Models
### [[Sequential consistency]] **strong consistency**
There is only one valid sequence. Make the sequence explicit in each process. Also think about [[Logical Clocks]], **at any point their logical clocks are the same.**
### [[Causal consistency]]  **relaxed sequential consistency**
### [[Entry consistency]] **Weak-consistency**
#### [[grouping operations]]

### [[Eventual Consistency]]

### This leads into [[Lamports Logical Clocks|Lamports Scalar-based Logical Clocks]]



