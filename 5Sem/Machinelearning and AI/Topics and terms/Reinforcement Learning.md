
> [!tip] **Reasoning behind** [[Reinforcement Learning]]
> We, and other intelligent beings, learn by interacting with our environment. We are goal-directed and we can learn without examples of the optimal behavior. **This differs from certain other types of learning.**
> - it is Active rather than passive
> - Interactions are often sequential - future interactions can depend on earlier ones
> 
> ![[image_Reinforcement Learning-1.png]]

> [!NOTE] **Important Concepts**
> We have an **agent** and an **environment**. 
> 1. The **agent** takes ***actions***
> 2. The **environment** responds with ***rewards***(*positive or negative*)
> 3. The **agent** receives ***observations*** from the **environment**
> 
> **Thus**, this requires os to be mindful of:
> - time
> - long and short term consequences of actions
> - Actively gathering experience
> - dealing with uncertainty
> 
> **<font color="red">EXPLORE & EXPLOIT!</font>**

### Quick example

> [!NOTE] RL for Go (*the board game*)
> - **Objective:** Win the fucking game
> - **State:** the position of all the pieces
> - **Action:** Where to put the next piece down
> - **Reward:** 1 if win at end of round, else 0

## Rewards
- A **REWARD** $R_{t}$ is a **scalar feedback signal**
	- Indicates how well agent is doing at time step 𝑡– **defines the goal**
	- The **agents** job is to maximize cumulative reward (**we call this the return**)
	-  **DEFINITION**: *Any goal can be formalized as the outcome of maximizing expected cumulative reward*.
#### Reward examples
- Fly stunt maneuvers in a helicopter
	- (*plus*) for following desired trajectory
	- (*minus*) for crashing
- Video or board game
	- (*plus*) score increased
	- (*minus*) score decreased
- Robot walk
	- (*plus*) forward motion
	- (*minus*) fell

Why rewards? Well! look at **Sequential Decision Making**
## Sequential Decision Making
- **Goal:** *Select actions to max total future reward*
- Actions may have long term consequences
- Reward may be delayed, so it may be better to sacrifice immediate reward to gain more long-term reward.
	- **Examples:**
		- A financial investment (may take months to mature)
		- Refueling a helicopter (might prevent a crash in several hours)
		- Blocking opponent moves (might help winning chances many moves from now)

# The System Components

> [!NOTE] Main components
> **Actor**, **Environment** and **time**
> **Actions**, **observations** and **rewards**
> - At each step $t$:
> 	- **the agent**:
> 		- Executes action $A_{t}$, receives observation $O_{t}$ and a scalar reward $R_{t}$
> 	- **the environment:**
> 		- Receives action $A_{t}$, emits observation $O_{t+1}$ and a scalar reward $R_{t+1}$
> - $t$ increments at env. step
> 

## The **History** and **State**
## History
The history is the sequence of observations, actions, rewards:
$$H_{t}=O_{1},R_{1},A_{1},\dots,A_{t},O_{t},R_{t}$$
**IN OTHER WORDS:** it is all the observable variables up to time $t$
And this influences what happens next: *The agent selects and action based on this history*, after which the environment selects observations/rewards

> [!NOTE] **State,** a function of **History**
> **State** is the information used to determine what happens next.
> Formally a function of **history**, described: $$S_{t}=f(H_{t})$$
> The **environment** and the **agent** have different states
> - **Env. State:** $S^{e}_{t}$ *private state* the environment uses to pick the next observation/reward. **Usually** not visible to the **agent**, and if it is it may contain irrelevant info(*to the agent*)
> - **Agent State:** $S^{a}_{t}$ agent’s internal representation (whatever info, which the agent uses to pick next **action**). Also the info used by our **RL algorithms** and, as said earlier, cab be **ANY** function of history.
> 
## State (and *[[Markov Decision Process (MDP)]]*)
### Markov states (*Information States*)
- An information state (a.k.a Markov state) contains all useful information from the history
- **DEFINITION:** A state $S_t$ is Markov if and only if: $$P[S_{t+1}\mid S_{t}] = P[S_{t+1} \mid S_{1},\dots, S_{t}]$$
- ***The future is independent of the past given the present***
-  <font color="red">Once the state is known, the history may be thrown away, i.e., the state is a sufficient statistic of the future</font>
### [[Markov Decision Process (MDP)]] and *partially observable Markov decision process (POMDP)*


> [!NOTE] Fully observable Environments (**[[Markov Decision Process (MDP)]]**)
> **Full observability: agent directly observes environment state**
> $O_{t}=S^{a}_{t}=S^{e}_{t}$
> - Agent state = environment state = information state


> [!NOTE] Partially observable Environments (**[[Markov Decision Process (MDP)|POMDP]]**)
> **Partial observability**: agent indirectly observes environment, i.e.:
> - A robot with camera vision isn’t told its absolute location
> - A trading agent only observes current prices
> - A poker playing agent only observes public cards
> 
> **so now,** $\text{AGENT}\neq \text{STATE}$ ,
> and therefore **agent** must construct its own state representation by using **History**, and its **BELIEFS**(probabilities) of the **environment state** 




> [!NOTE] Quick intro to [[Reinforcement Learning]]
> Regular Machine Learning is primarily a collection made of [[Supervised Learning]], [[Unsupervised Learning]] and [[Reinforcement Learning]]
> 
> **However**, **[[Reinforcement Learning]]** is in itself a collection of ideas from different disciplines. Stuff like these: (from: *Engineering, Com.Sci, Neuroscience, Psychology, Economics, Math*)
> - **Reward System**
> - **Classical/Operant Conditioning**
> - **Bounded Rationality**
> - **Operations Research** 
> - **Optimal Control** 
> ![[image_Reinforcement Learning.png]]