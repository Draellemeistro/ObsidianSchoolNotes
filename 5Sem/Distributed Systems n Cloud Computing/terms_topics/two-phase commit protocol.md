
> [!NOTE] [[two-phase commit protocol]] (2PC)
> In a two-phase commit protocol, a coordinator first checks whether all processes agree to perform the same operation (i.e., whether they all agree to commit), and in a second round, multicasts the outcome of that poll.

##### Essence
The client who initiated the computation acts as **coordinator**; processes required to commit are the **participants**
- **phase 1a:** Coordinator sends `VOTE-REQUEST` to participants (also called a **pre-write**)
- **phase 1b:** when participant receives `VOTE-REQUEST` it returns either `VOTE-COMMIT` or `VOTE-ABORT` to coordinator. If it sends `VOTE-ABORT`, it aborts local computation.
- **phase 2a:** Coordinator collects all votes; if all are `VOTE-COMMIT`, it sends `GLOBAL-COMMIT` to all participants, otherwise it sends `GLOBAL-ABORT`
- **phase 2b:** each participant waits for `GLOBAL-COMMIT` or `GLOBAL-ABORT` and handles accordingly.
![[image_Failure-Detection-1.png]]
#### Finite State Machines for 2PC
##### FSM: Coordinator
![[image_Failure-Detection-2.png]]
##### FSM: Participant
![[image_Failure-Detection-3.png]]
#### (2PC) - Failing participant
#COMEBACK 
![[image_Failure-Detection-4.png]]![[image_Failure-Detection-5.png]]
#### (2PC) - Failing Coordinator
![[image_Failure-Detection-6.png]]

