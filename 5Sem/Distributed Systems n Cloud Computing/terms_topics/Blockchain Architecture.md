- Blocks are organized into an unforgeable append-only chain 
- Each block in the blockchain is immutable => massive replication 
- The real snag lies in who is allowed to append a block to a chain 
- A single entity decided on which validator can go ahead and append a block
### Appending a block: distributed consensus
- A selected, relatively small group of server jointly reach consensus on which validator can go ahead
- Non of these servers need to be trusted as long as roughly two-thirds behave according to their specifications 
- In practice only a few tens of servers can be accommodate 
- Participants collectively engage in a leader election. Only the elected leader is allowed to append a block of validated transactions. 
- Large scale, decentralised leader election that is fair, robust, secure and so on, is far from trivial.

A decentralized, hybrid system where decentralization plays a key role in managing a distributed ledger.
Blocks are organized into an **unforgeable append-only** chain. 
Each block in the blockchain is immutable ⇒ massive replication
> [!NOTE] The real snag lies in who is allowed to append a block to a chain
### [[Consensus]] in Blockchain (distributed consensus)

##### Centralized Solution
> [!NOTE] A single entity decides on which validator cango ahead and append a block. **Does not fit the design goals of blockchains.**
##### Distributed solution (Permissioned)
A selected, relatively small group of servers jointly reach consensus on which validator can go ahead.
None of these servers needs to be trusted, as long as roughly two-thirds behave according to their specifications.
In practice, only a few tens of servers can be accommodated.
##### Distributed solution (Permissionless)
Participants collectively engage in a [[Leader Election]]. Only the elected leader is allowed to append a block of validated transactions 

Large-scale, decentralized [[Leader Election]] that is fair, robust, secure, and so on, is far from trivial.