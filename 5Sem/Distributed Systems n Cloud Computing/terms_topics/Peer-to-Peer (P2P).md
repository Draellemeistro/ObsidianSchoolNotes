**Also known as Symmetrically Distributed Architectures** 
Processess(peers) have equal roles and communicate within an [[overlay network]]. Can be Structured or Unstructured.

**Processes are all equal**: The functions that need to be carried out are represented by every process -> Each process will act as a client and a server at the same time (i.e., acting as a servant)

[[P2P-search]]

## Structured
Uses determisitic schemes for routing messages (e.g., consistent hashing).
Make use of a --**semantic-free index**-- Each data item is uniquely associated with a key, in turn used as an index. Common practice: use a hash function (key(data item)=hash(data item's value). P2P system now responsible for storing (key,value) pairs) 
> [!NOTE] **Chord:** A Structured [[Peer-to-Peer (P2P)]] syste
> Nodes are logically organized in a ring. Each node has an 'm'-bit IDENTIFIER. Each data item is hashed to an 'm'-bit key. Data item with key 'k' is stored at node with smalles identifier id >= 'k', called the SUCCESSOR of key 'k'. The ring is extended with various shortcut links to other nodes.

## Unstructured
Peers are connected randomly; search algorithms are sued to locate data or other peers.
Each node maintains an ad hoc list of neighbors. The resulting overlay resembles a RANDOM GRAPH: an edge <u,v> exists only with a certain probability P\[<u,v>]
### Searching in Unstructered [[Peer-to-Peer (P2P)]]
> [!NOTE] **Flooding ---- Random walk**
> Random walks are more [[Distributed-Communication]] efficient, but may take longer before they find the result.
> ![[image_Peer-to-Peer (P2P).png]]
#### Flooding
Issuing node 'u' passes request for 'd' to all neighbors. Request is ignored when receiving node had seen it before. Otherwise, 'v' searches locally for 'd' (recursively). May be limited by a TIME-TO-LIVE(a max number of hops)
#### Random Walk
Issuing node 'u' passes request for 'd' to randomly chosen neighbor, 'v'. If 'v' does not have 'd', it forwards request to one of its own randomly chosen neighbors, and so on.

## [[Super-peer networks]]
![[image_Peer-to-Peer (P2P)-1.png]]
**It can be sensible to break the symmetry in pure P2P networks. Super peers participate in the P2P, each having weak peers as "sub nodes"**
When searching in unstructured P2P systems, having **index servers** improves performance.

Deciding where to store data can often be done more efficiently through **brokers**.

## Collaboration: The BitTorrent case
> [!NOTE] **Principle:** search for a file F
- Lookup file at a global directory ⇒ returns a torrent file
- Torrent file contains reference to tracker: a server keeping an accurate account of active nodes that have (chunks of) F
- P can join swarm, get a chunk for free, and then trade a copy of that chunk for another one with a peer Q also in the swarm.
![[image_Peer-to-Peer (P2P)-2.png]]
