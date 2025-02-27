[RIGTIG GODE TIL E-VOTING](https://www.researchgate.net/publication/290947569_Modeling_Threats_of_a_Voting_Method)
https://www.researchgate.net/publication/290947569_Modeling_Threats_of_a_Voting_Method


https://ieeexplore-ieee-org.zorac.aub.aau.dk/document/9768251


https://ieeexplore-ieee-org.zorac.aub.aau.dk/document/9768253


> [!SUMMARY] Kig på:
> - HELIOS
> 	- [ScienceypaperBS](https://www.usenix.org/legacy/events/sec08/tech/full_papers/adida/adida.pdf)
> 	- [github.HELIOS](https://github.com/benadida/helios)
> 	- [HELIOS voting](http://www.heliosvoting.org/):
> - [Swiss Post Voting System - System specification](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation/-/blob/master/System/System_Specification.pdf) 
> - Belenois


> [!abstract] 
> **DE VIGTIGSTE OVERVEJELSER I ET E-VOTING SYTEM:**
> - **verifiability**. Verifiability typically includes:
> 	- **individual** verifiability (a voter can check that her ballot is counted);
> 	- **universal** verifiability (anyone can check that the result corresponds to the published ballots);
> 	- **eligibility** verifiability (only legitimate voters may vote).
> - **vote privacy**: no one should know how I voted;
>  
> ==These two goals are often seen as antagonistic and some national agencies even impose a hierarchy between them: first privacy, and then verifiability as an additional feature.==
> 
> **[De her](https://research.cyber.ee/~janwil/publ/ivxv-evoteid.pdf) opdelte det i fire dele ifht. sikkerhed:**
> - integrity
> 	- observers help us to assure that the secure procedure for the voting method was correctly put into practice
> - confidentiality
> - transparency
> - coercion-resistance.

> [!ABSTRACT] ten basic rules for Estonian elections: ([kilde](https://www.researchgate.net/publication/290947569_Modeling_Threats_of_a_Voting_Method))
> - **Authenticity**: only eligible voters are allowed to vote.
> - **Freedom**: each voter can vote according to his/her free will.
> - **Directness**: voter votes in person.
> - **Generality**: there are opportunities for the entire adult citizenry to participate in voting.
> - **Uniformity**: each voter has one and only one vote.
> - **Ballot secrecy**: nobody besides the voter him-/herself knows how he/she voted.
> - **Correctness**: election result is correctly calculated on the basis of cast votes. 
> - **Conﬁdentiality**: election result is published only after the voting has ended.
> - **Availability**: voting methods are available.
> 

> [!end-to-end verifiable voting]
> should provide the following properties:
> 1. **Cast as intended:** The voter is able to check that her ballot represents a vote for the candidate to whom she intended to give the vote.
> 2. **Well-formedness:** Anyone is able to check that valid ballots do not contain over-votes or negative votes.
> 3. **Recorded as cast:** The voter can check that her ballot is recorded as she cast it.
> 4. **Tallied as recorded:** Anyone is able to check that all the recorded ballots have been tallied correctly
> 5. **Consistency:** Anyone is able to check that the voters and the general public have the same view of the election records
> 6. **Authenticity/eligibility:** Anyone can check that any cast ballot has a corresponding voter who can perform check No. 3.
> 
> Introducing an individual verifiability tool addressed **items 1 and 3** above
> - These are also the two requirements that are targeted towards the voter herself and are hence relatively straightforward to implement.
> - The remaining four requirements (often referred to as universal verifiability) refer to Anyone as a potential verifier.
> 	- The exact meaning of this term is vague. we need to make it clearer before actual implementation.



> [!abstract] Homomorphic encryption and blockchain technology
> Homomorphic encryption and blockchain technology are regarded as two significant technologies for improving e-voting systems.
> 
> **==Homomorphic encryption guarantees ballot verifiability and result verifiability== of votes while the ==blockchain technology promises integrity and transparency==**
> 
> **==WEAKNESS:==** voters cannot be certain that the cast votes are the same as the encrypted forms, Because the cast votes are encrypted in the form of a cipher text.
> [HERFRA](https://arxiv.org/pdf/2111.05096.pdf)

> [!Blockchain] 
> Blockchain is a distributed and decentralized public ledger managed by a peer-to-peer network. Once the data in one block undergoes change, the revision process is recorded and shared by all the other blocks in the blockchain system. In other words, it is impossible to amend the data secretly. This is a clear advantage in an e-voting system because blockchain itself can monitor whether the voting results are manipulated by external forces. Any forced revision of data is detected immediately. The transparency of a blockchain network leads to credibility of the total e-voting system. Moreover, the main characteristic of blockchain system, especially public blockchain, is that its network is decentralized. Decentralized networks avoid reliance on any central authority; decisions for the total system are made by a majority of the members in the network. Decentralization of blockchain networks can prevent any possible corruption of total e-voting systems created by central authorities.

> [!Homomorphic Encryption]
> [Homomorphic encryption](https://crypto.stanford.edu/craig/craig-thesis.pdf) guarantees data security by eliminating the need to send plain data
> - **has weaknesses that hinder practical implementation:**
> 	- Data that deploys homomorphic encryption cannot help but require large capacity
> 	- speed of encrypting plain data and of computing encrypted data are not fast enough to be practical
> 	- The accuracy of homomorphic encryption for large-scale data is also in doubt because the noise, that occurs with every computation, eventually becomes too large to ignore.


> [!Point] 
> [kilde](https://royalsocietypublishing.org/doi/10.1098/rsta.2008.0149): **software-independent voting systems should be preferred, and _software-dependent_ voting systems should be avoided.**


> [!NOTE] Hvorfor vote privacy vigtigt?
> fra kilde: [Breaking and Fixing Vote Privacy of the Estonian E-Voting Protocol IVXV](https://orbilu.uni.lu/bitstream/10993/49442/1/main.pdf)
> vote privacy is a universal right. All voters, not just the majority of them, **==must have the right to express their true will without facing personal negative consequences.==**
> even if vote privacy of only a fraction of the electorate can be broken, no voter can be sure whether or not she is among the targeted voters. **==The mere possibility of these attacks can cause a significant bias in the election result and thus undermine the legitimacy of the government elected.==**


> [!Inspiration]
> **==the Data Auditor==**  To perform this verification. will **verify the decryption proofs** exported during the vote decryption phase. this process must not violate the secrecy of the votes.
> - To enable flexible decryption proofs, the cryptosystem used for vote encryption **RSA-OAEP  is replaced by a Randomized homomorphic public-key algorithm**, e.g. ElGamal
> 	- This makes it possible to prove correct decryption while preserving privacy, ==using re-encryption mixnets such as [this](https://link.springer.com/chapter/10.1007/978-3-642-29011-4_17), [this](https://eprint.iacr.org/2015/1112) or [this](https://www.csc.kth.se/~dog/research/papers/TW10Conf.pdf)==
> 
> to fix **i-ballot box integrity issues**, an extra commitment step will be added.
> - **==Registration Service==** will implement this. will essentially keep a ledger of the stored i-votes.
> - makes it **possible to outsource the duty of collecting votes** to a third party, as there is a **way to ensure that the integrity of the i-ballot box** is maintained.



> [!short summary of the failures observed]
> 
> [How not to prove your election outcome](https://ieeexplore.ieee.org/document/9152765): Using sophisticated cryptographic protocols without a proper consideration of what properties they offer, and under which conditions, can introduce **==opportunities for undetectable fraud even though the system appears to allow verification of the outcome==**
> 
> Many of the components have been proven secure elsewhere, but under assumptions that are not realised in this system
> 1) **Statically secure primitives are used in an adaptive setting**. The sVote system uses Maurer’s unified proofs framework ==[1]== for many of its ZKPs. These are proven to offer security in an interactive and static model (_i.e._ when the statement is given to the prover), but are used in sVote in a setting where the prover can choose the statement afterwards, thus making it vulnerable to the pitfall described in ==[2].==
> 2) **The facts proven in the ZKPs are not sufficient. A** ZKP proves a particular statement (or more precisely, membership of a specific language). But in sVote, the conjunction of the facts proven by the voting client is not sufficient to imply the desired properties about the votes.
> 3) **The multiparty protocol isn’t secure against collusion.** sVote uses an original multiparty protocol to compute the codes to be returned to voters. The protocol has five authorities and is intended to tolerate some dishonest participants. We show that one of them can misbehave alone (with a cheating client) and break verifiability.
> 4) **Hardness assumptions are not guaranteed.** Most of the protocols used in sVote rely on the hardness of some computational problems. For instance, in various places, it is expected that discrete logs of various group elements in various bases are unknown. However, sVote offers no evidence of how the group parameters and group elements are generated, which makes it impossible to verify whether a prover may know a trapdoor that would violate the specific instances of the computational problems used in the system. This can be used to violate both individual and universal verifiability in sVote.
> 
> **Every one of these errors allows a successful vote manipulation that passes verification, though in some cases it is informally clear that something has gone wrong.
## Attacks

> [!NOTE] Commonly 
> ![[Pasted image 20240303051740.png]]
> ![[Pasted image 20240303051820.png]]



> [!NOTE] Attacks
> - **[Privacy Attacks](https://orbilu.uni.lu/bitstream/10993/49442/1/main.pdf)**
> 	- shifting attacks 
> 	- encoding attacks
> - **[Replay attacks](https://eprint.iacr.org/2022/743)**
> 	- Basic replay attacks
> 	- Homomorphic replay attacks
> 	- Re-voting replay attacks
> - **[clash attacks](https://eprint.iacr.org/2012/116)**

> [!Attacks]
> **attacks on the i-ballot box integrity**
> 1. adding votes to the box
> 2. removing votes from the box
> 3. modifying votes already in the box
> 
> **Attacks on tabulation**
> 1. i-ballot box replacement
> 2. tabulation tool compromise
> 3. forgery of the voting result
> herfra: [kilde](https://research.cyber.ee/~janwil/publ/ivxv-evoteid.pdf)

> [!attacks on tabulation]


> [!Replay attacks]
> **Replay attacks are among the most well-known attacks against vote privacy. ==Many e-voting systems have been proven vulnerable to replay attacks==, including systems like ==Helios== that are used in real practical elections.**
> 
> **==replay attacks can be devastating for a voter's privacy even when an adversary's resources are very limited.==** contrary to a common belief, replay attacks can be very efficient and must therefore be considered a serious threat.
> **TYPES:**
> - Basic replay attacks
> - Homomorphic replay attacks
> - Re-voting replay attacks

> [!Formal Proofs]
> formal proofs are not useless—they are important for clarifying assumptions and security claims, and they provide an argument (which can be checked) for why the system should be trusted. However, proofs themselves can be mistaken or insufficient. They should be required, but they are a part of the scrutiny process not a substitute for open scrutiny.

> [!Closing thoughts]
> We hope this work can help customers assess what does, and does not, constitute genuine verifiable computation. **==There is nothing gained by using a proven-secure component if its assumptions are not met in the context in which it is used==**==. Nor is there any advantage to sound ZKPs if they do not actually prove what is needed in the rest of the protocol.==
> 
> **==The aim of verifiable election software is verifiable election outcomes, not proofs that pass==**. **If the system itself does not come with meaningful evidence** that its verification procedure is sound, then an **apparently-successful verification implies nothing about the integrity of the election result.

> [!Hurtigt referat]
>  [Breaking the encryption scheme of the Moscow Internet voting system](https://arxiv.org/abs/1908.05127): We show **two successful attacks on the encryption scheme implemented in the voting system**
> 
> **The encryption used in this system is a variant of ElGamal over finite fields.** 
> - **In the first attack**
> 	- The used key sizes are too small. We explain how to retrieve the private keys from the public keys in a matter of minutes with easily available resources.
> -  After a fix, we found **the second attack**: 
> 	- The new implementation was not semantically secure. 
> 	- This newly found security vulnerability can be used for counting the number of votes cast for a candidate.

> [!Lessons learned] 
> 1. Designers should be careful when using cryptography
> 2. Using a blockchain is not enough to guarantee full transparency
> 
> **ALSO**
> ==This is a good example of the difficulty for an Internet voting system to make the **vote secrecy rely uniquely on cutting the link between the voters and their encrypted ballots when they arrive on a server that should also authenticate the voters.**== What is really required is to cut the link with the vote in clear, and, for this, classical methods exist like homomorphic decryption or verifiable mixnets. In such a high-stakes election, many seemingly incompatible security properties must be satisfied (secrecy vs transparency), and advanced cryptographic tools are almost impossible to avoid.



> [!Belenios explained]
> - Belenios is built upon Helios. 
> - Like in Helios, the voters can check that their ballots appear on the bulletin board, and that the result corresponds to the ballots on the board, while vote secrecy is guaranteed. 
> - In addition, Belenios provides eligibility verifiability: anyone can check that ballots come from legitimate voters, 
> 	- whereas in Helios, a dishonest bulletin board could add ballots without anyone noticing. Helios is thus vulnerable to ballot stuffing. 
> 	- **Eligibility verifiability can be added to voting systems through a signature mechanism and additional credentials**
> - like in Helios, Belenios is not coercion-resistant: voters may prove for whom they voted by providing the randomness used to produce their ballot or they may simply sell their voting material. Therefore Belenios should not be used in high stake elections.