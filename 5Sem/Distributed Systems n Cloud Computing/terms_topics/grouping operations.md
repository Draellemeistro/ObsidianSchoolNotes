- accesses to **synchronization variables** are [[Sequential consistency|Sequential consistent]].
- No access to a synchronization variable is allowed to be performed until all previous writes have completed EVERYWHERE.
- No data access is allwed to be performed until all previous accesses to synchronization variables have been performed
### Basic Idea
You don't care that reads and writes of a series of ops are immediately known to other processes. You just want the effect of the series itself to be known

**Why?** bottleneck and performance, most likely
![[image_grouping operations.png]]
### Weak Consistency [[Entry consistency]] ??
Implies that we need to lock and unlock data (implicitly or not)
### Question 
> [!question] **QUESTION**
> What Would be a convenient way of making this consistency more or less transparent to programmers?

Less transparency can allow programmers to optimize the efficiency and performance of the read writes. the clear drawback is that you can screw up, (so maybe have it more transparent, dummy?)