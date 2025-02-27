> [!fail] **[[Byzantine failures]]** represent the most general and challenging class of failures, where nodes may behave maliciously or arbitrarily, potentially due to compromise or adversarial intent. **3k + 1**

Byzantine [[arbitrary failure]]

> [!NOTE] Why having 3k processes is not enough
> ![[image_Byzantine failures.png]]
> Impossibility to reach [[Consensus]] with 3 processes and trying to tolerate a single arbitrarily failing process.
> ![[image_Byzantine failures-1.png]]
> Reaching consensus with 4 processes, of which one may fail arbitrarily


## [[Consensus]] under [[arbitrary failure]] (i think its [[Byzantine failures]])
**essence:** we consider process groups in which communication between process is **inconsistent.** 
![[image_Consensus.png]]
#### **Observation:**  **it fucking lies**
This is a different behaviour from what we saw before. In the previous examples, the arbitrary node was simply voting differntly than the others, it was not behaving **_"maliciously"_** 
### System model
- we consider a **primary** $P$ and $n-1$ **backups:** $B_{1},\dots,B_{n-1}$
- A client sends $v\in \{T,F\}$ to $P$ 
- messages may be **lost**, but this can be detected
- messages **cannot be corrupted** beyond detection
- A receiver of a message can **reliably detect its sender.**
#### **Byzantine agreement:** requirements
- **BA1:** Every nonfaulty backup process stores the same value.
- **BA2:** If the primary is nonfaulty then every nonfaulty backup process stores exactly what the primary had sent
#### Observation
- **Primary faulty** $\to$ BA1 says that backups may store the same, but different (and thus wrong) value than originally sent by the client.
- **Primary not faulty** $\to$ satisfying BA2 implies that BA1 is satisfied.