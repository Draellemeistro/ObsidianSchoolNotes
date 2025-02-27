
> [!NOTE] What is it? **ELI5**
> - The process of creating maintaining multiple copies (replicas) of data across distributed systems.
> - Enhances system **Reliability** and **performance** by ensuring data availability and reducing acess latency. we gotta keep that shit [[Consistency|Consistent]] though.
> 
> (*Also, check out the sister term, [[Consistency]]*) 
- [[Replica Management]]
    - Placement
    - Caching

## But why?
Assume a simple model in which we make a copy of a specific part of a system (meaning code and data.)
- **Increase Reliability:** If one copy does not live pu to specs, siwtch over to the other copy while repairing the failing one.
- **Performance:** Simply spread requests between different replicated parts to keep load balanced, or to ensure quick response by taking proximirt inro account.

> [!NOTE] **The problem**
> Having multiple copies, means that when any copy changes, that change should be made at all copies: **replicas need to be kept the same,** that is, be kept **CONSISTENT**

### Performance and Scalability
**Main Issue:** To keep replicas consistent, we generally need to ensure that all conflicting operations are done in the same order everywhere.


> [!NOTE] **Conflictiong operations: From the world of transactions**
> - **read-write conflict:** a read operation and a write operation act concurrently
> - **Write-write conflict:** Two concurrent write ops
> 
> **Issue:** Guaranteeing global ordering on conflicting ops may be a costly operation, downgrading *scalability*
> **SOLUTION:** weaken [[Consistency]] requirements so that hopefully global synchronization can be avoided
>  



