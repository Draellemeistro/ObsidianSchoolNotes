[Security Analysis of the Estonian Internet Voting System](https://dl.acm.org/doi/10.1145/2660267.2660315)
### [[Samling af nogle vigtige ideer]]

# Artikler gennemgået her

- 2021/2022: Gitlab [E-voting documentation](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation)
- 2008: [On the notion of ‘software independence’ in voting systems](https://royalsocietypublishing.org/doi/10.1098/rsta.2008.0149)
- 2022: [Breaking and Fixing Vote Privacy of the Estonian E-Voting Protocol IVXV](https://orbilu.uni.lu/bitstream/10993/49442/1/main.pdf)  springer: [link](https://link.springer.com/chapter/10.1007/978-3-031-32415-4_22)
- 2022: [How Efficient are Replay Attacks against Vote Privacy? A Formal Quantitative Analysis](https://eprint.iacr.org/2022/743)
- [Clash Attacks on the Verifiability of E-Voting Systems](https://eprint.iacr.org/2012/116)
- 2002: [Coercion-Resistant Electronic Elections](https://eprint.iacr.org/2002/165.pdf)
- 2016: [Improving the verifiability of the Estonian Internet Voting scheme](https://research.cyber.ee/~janwil/publ/ivxv-evoteid.pdf)
- 2020: [How not to prove your election outcome](https://ieeexplore.ieee.org/document/9152765)
- 2019: [Breaking the encryption scheme of the Moscow Internet voting system](https://arxiv.org/abs/1908.05127)
- 2010: [Attacking and fixing Helios: An analysis of ballot secrecy](https://eprint.iacr.org/2010/625)
- 2018: [Voting: You Can’t Have Privacy without Individual Verifiability](https://inria.hal.science/hal-01858034/document)
- 2020: [How to fake zero-knowledge proofs, again](https://inria.hal.science/hal-02928953/document)
- 2019: [Belenios: a simple private and verifiable electronic voting system](https://inria.hal.science/hal-02066930/document)
- 2022: [A privacy attack on the Swiss Post e-voting system](https://inria.hal.science/hal-03446801/file/rwc.pdf)

## - 2021/2022: Gitlab [E-voting documentation](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation)
## - 2008: [On the notion of ‘software independence’ in voting systems](https://royalsocietypublishing.org/doi/10.1098/rsta.2008.0149)

voting system is _software ==independent_== **if an (undetected) change or error in its software cannot cause an undetectable change or error in an election outcome’**

It is proposed that **software-independent voting systems should be preferred, and _software-dependent_ voting systems should be avoided.**

 consider a direct-recording electronic (DRE) voting system that typically provides a touch-screen user interface for voters to make selections and cast ballots, and stores the cast vote records in memory and on a removable memory card. A DRE may display an essentially infinite variety of different ballot layouts, and may include complex accessibility features for the sight impaired (e.g. so that a voter could use headphones and be guided to make selections using an audio ballot).

 pure DRE voting system produces only electronic cast ballot records that are not directly observable or verifiable by the voter.
 
 **no meaningful audit of the DRE's electronic records to determine their accuracy is possible;** accuracy can only be estimated by a variety of other (imperfect) measures, such as comparing the accumulated tallies with pre-election canvassing results, performing software code reviews and testing the system accuracy before (or even during) the election.

### Andre ting i artiklen:
##### (a) The difficulty of evaluating complex software for errors
sss
##### (b) The need for software-independent approaches
sss
#### 3. Definition and rationale for software independence
sss
##### (a) Refinements and elaborations of software independence
##### (b) Examples of software-independent approaches

#### 4. How does one test for software independence?
##### (a) Are other software-dependent alternatives sufficient?
##### (b) Implications for testing and certification

##### (c) Related issues
#### Conclusion
**The ability to prove the correctness of software diminishes rapidly as the software becomes more complex**. effectively be impossible to adequately test future (and current) voting systems for flaws and introduced fraud, and thus these systems would always remain suspect in their ability to provide secure and accurate elections.

**A _software-independent_ approach to voting systems will provide voters with an assurance that errors or fraud in election results can reliably be detected.** Testing costs to prove the correctness of the software can be held somewhat in check if the correctness of the election results does not rely on the correctness of the software.

## - 2022: [Breaking and Fixing Vote Privacy of the Estonian E-Voting Protocol IVXV](https://orbilu.uni.lu/bitstream/10993/49442/1/main.pdf)  springer: [link](https://link.springer.com/chapter/10.1007/978-3-031-32415-4_22)

e e-voting protocol IVXV that is used for legally binding political elections in Estonia from a **privacy perspective.** **==It is vulnerable to attacks against vote privacy==** in those threat scenarios that were considered for IVXV originally.
**We explain how to improve IVXV so that it protects against the privacy issues we discovered**

The initial e-voting system used for political elections in Estonia was a rather naive system whose security relied on trusted voting authorities; in particular, that system did not allow for auditing the correctness of the election result.

### IVXV employs the following cryptographic primitives:
- **A digital signature scheme** S = (KeyGen$_S$ , Sign, Verify) for signing ballots and for signing all public data output by the election authorities.
- **A homomorphic public-key encryption scheme** E = (KeyGen$_E$ , Enc, Dec) for encrypting the voters’ plain choices. In the IVXV implementation, E is instantiated with the ElGamal PKE scheme
- **A proof of shuffle** $π_{Shuffle}$ which is generated by MS to prove that it shuffled its input ciphertexts correctly. In the IVXV implementation, $π_{Shuffle}$ is instantiated with Verificatum
- A proof of correct decryption $π_{Dec}$ which is generated by EO to prove that it decrypted the final ciphertexts correctly. In the IVXV implementation, πDec is instantiated with a Schnorr-based NIZKP to prove knowledge of discrete logarithms
In the original IVXV paper, **it had not been specified which security properties these primitives need to provide** precisely but the respective instantiations suggest that the signature scheme S, the encryption scheme E, the proof of shuffle $π_{Shuffle}$ and the proof of correct decryption $π_{Dec}$ are **==supposed to be EUF-CMA-secure, IND-CPA-secure, and non-interactive zero-knowledge proofs (NIZKPs), respectively==**

### Protocol phases

- **Setup phase**
	- The protocol assumes that there exists a public-key infrastructure (PKI) of public verification keys for individual voters.
	- The Election Organizer EO determines the list of eligible voters which are identified by their respective public verification keys
	- EO also determines the set of valid choices C
	- EO runs the key generation algorithm of the public-key encryption scheme E to obtain an encryption/decryption key pair. **lbalbla** The list of eligible voters, the set of valid choices C, as well as the public key pk are made available to everybody.
- **Submission phase**
	- Each voter who wants to vote for some choice encrypts her choice
	- then signs the ciphertext c with her secret signing key
	- and submits the resulting pair to the Vote Collector VC
	- For each incoming ballot, VC verifies whether is a valid signature for SDASD
	- If this is the case, then VC stores b together with the time at which it had been submitted. Voters can re-vote multiple times.
- **Tabulation phase**
	- After the submission phase has closed, VC forwards the list of ballots to the I-Ballot Box Processor IBBP who first verifies that all ballots in VC’s list were signed by eligible voters only.
	- Afterwards, IBBP removes the ballots of all voters who have also submitted a paper vote
	- Eventually, IBBP extracts the last submitted ballot of each voter (who did not submit a paper vote), removes the respective signatures, and stores the resulting ciphertexts in a list
	- The I-Ballot Box Processor sends the list of ciphertexts B1 to the mixing service MS which then re-encrypts all ciphertexts in B1, shuffles the resulting re-encrypted ciphertexts uniformly at random, and computes a proof of correct shuffling
	- After that, MS sends the resulting ciphertext vector B2 to EO which first uses its secret decryption key sk to decrypt all ciphertexts in B2 to obtain the final result res, and then computes a proof of correct decryption πDec to prove that it decrypted B2 correctly.
- **Auditing phase**
	- s

1. In the setup phase, EO creates the key material. 
2. In the submission phase, voters can submit their ballots. 
3. In the tabulation phase, the ballots submitted by the voters are anonymized and decrypted. 
4. In the auditing phase, which can be executed at any point after the election result has been announced, the correctness of the data output by the election authorities can be verified externally

### Privacy Attacks
**two attacks against vote privacy of IVXV**:
- shifting attacks 
- encoding attacks
Both attacks exploit the homomorphic property of the encryption scheme, that is employed to create maliciously generated ballots that depend on honest voters’ ballots.
**Both attacks slightly differ in terms of the underlying assumptions and their impact**: in comparison to the shifting attack, the **encoding attack requires qualitatively stronger assumptions** **==but it allows to break privacy of several voters by submitting a single malicious vote.==**

#### shifting attacks 
The idea of the shifting attack is to submit a ballot which contains a vote for ch' if and only if the targeted voter V submitted a vote for ch.
If ch' is an unpopular choice, then the adversary learns whether or not V voted for ch by checking whether there exists a vote for ch' in the final election result.

**Assumptions**
We make the following assumptions:
1. The attacker can learn the ballot of the voter V whose privacy he wants to break. 
2. There exists a (valid) choice ch' ∈ C which is chosen by none of the (honest) voters with high probability (see 2nd paragraph in Sec. 4.1). 
3. The attacker can control one voter.

**Impact**: 
The attacker can check whether V voted for ch.

**Program**:
The attacker runs the following program:
1. Submission phase: Learn ballot b of voter V
2. Submission phase: Submit ballot b'
3. After election: Check whether something 

#### Encoding attacks
The idea of the encoding attack is to submit a ballot which encrypts a unique encoding of the choices $ch_1,\dots,ch_k$ submitted by the targeted voters $V_1,\dots,V_k$
The attacker then checks for all possible combinations $ch'_1,\dots,ch'_k$  whether there exists an encoding of these choices in the final result. If the attacker finds such a combination, then he knows that $V_1,\dots,V_k$ voted for $ch'_1,\dots,ch'_k$

**Assumptions**
We make the following assumptions:
1. The attacker can learn the ballots of the voters  $V_1,\dots,V_k$ whose privacy he wants to break.
2. The attacker can learn the raw election result res.
3. The attacker can control one voter.

**Impact**: The attacker learns how $V_1,\dots,V_k$ voted

**Program**: 
The attacker runs the following program:
1. Submission phase: Learn ballots $b_1,\dots,b_k$ of voters $V_1,\dots,V_k$
2. Submission phase: Submit ballot $b'$
3. after election:
### Discussion and Conclussion
The IVXV protocol was explicitly designed in such a way that it “allows to outsource the vote collection task to a third party, as the correct operation of this party is verifiable by voters, third-party auditors and auditors nominated by the election organizer itself.
**the fact that they claimed that any third party could perform this task implies that VC should also not be trusted in terms of vote privacy.** ==Since VC receives all incoming messages, an attacker who controls VC can learn all submitted ballots (even if he cannot manipulate them undectably)==

we think that it is undesirable 6 having to trust a party (VC) for vote privacy whose original purpose/role is not to protect vote privacy (but to simply collect votes). since collected votes are not published in IVXV, **==it is questionable whether all parties (voters, observers, etc.) can have the same view on the data being processed, which is a crucial property for secure e-voting in general==**

**For the shifting attack**, we assume that there exists at least one unpopular choice (and that the attacker knows a priori that this choice is unpopular). this assumption is realistic.

**For the encoding attack**, we assume that the attacker can learn the “raw” election result which also contains invalid plain choices. **the IVXV protocol was explicitly designed in such a way that a possibly corrupted auditor is not able to learn how individual voters voted** learning the raw election result is clearly within the threat scenario considered for IVXV originally.

**It is realistic to assume that the attacker can control a voter** because the attacker can be an eligible voter herself. For the same reason, in case some voters collude, the attacker can execute the privacy attacks multiple times to target even more voters and break their vote privacy.

#### Implications
In democratic elections, ==**vote privacy is a universal right**==: the individual vote of each single voter must remain secret. All voters, not just the majority of them, **==must have the right to express their true will without facing personal negative consequences==**. it is particularly important to protect the privacy of those voters who favour less popular parties.

**==For example==**, a party of an ongoing trial may want to learn the judge’s personal political orientation in order to increase its advantage in the court or to blame the judge being biased.

**==even if vote privacy of only a fraction of the electorate can be broken, no voter can be sure whether or not she is among the targeted voters.==** This observation can be exploited to coerce many voters at the same time (not) to vote for a specific party because each coerced voter will likely follow the coercer’s instruction if she knows that the coercer can randomly check whether or not she obeyed.

**==The mere possibility of these attacks can cause a significant bias in the election result and thus undermine the legitimacy of the government elected.==**

#### Protection



##### Recommendations:

1. Voters in IVXV use a NIZKP $π_{Enc}$ as described above.
2. The (fixed) IVXV protocol is presented in full technical details.
3. The threat scenarios for all security properties (verifiability, privacy, coercionresistance) are described explicitly. Security is formally proven.
## - 2022: [How Efficient are Replay Attacks against Vote Privacy? A Formal Quantitative Analysis](https://eprint.iacr.org/2022/743)
### primære pointer / emner 

> [!NOTE] ting de indblander
> - **Different privacy definitions**
> - **Different replay attacks**


**Replay attacks are among the most well-known attacks against vote privacy. ==Many e-voting systems have been proven vulnerable to replay attacks==, including systems like ==Helios== that are used in real practical elections.**

**==replay attacks can be devastating for a voter's privacy even when an adversary's resources are very limited.==** contrary to a common belief, replay attacks can be very efficient and must therefore be considered a serious threat.
### Kategorier af replay attacks
- Basic replay attacks
- Homomorphic replay attacks
- Re-voting replay attacks

- ==måske brugbart:==
	- ![[Pasted image 20240302213610.png]]
	- ![[Pasted image 20240302213652.png]]


## - [Clash Attacks on the Verifiability of E-Voting Systems](https://eprint.iacr.org/2012/116)
**==Verifiability==** is a central property of modern e-voting systems. Intuitively, verifiability means that voters can check that their votes were actually counted and that the published result of the election is correct, even if the voting machine/authorities are (partially) untrusted.

The **==main idea behind clash attacks==** is that voting machines manage to provide different voters with the same receipt. As a result, the voting authorities can safely replace ballots by new ballots, and by this, manipulate the election without being detected.

though the attack is quite simple, **under reasonable trust assumptions, it applies to several e-voting systems that have been designed to provide verifiability**. ==In particular==, we show that it applies to the prominent ==ThreeBallot== and ==VAV== voting systems as well as to two e-voting systems that have been deployed in real elections: the ==Wombat Voting system== and a ==variant of the Helios ==voting system.
## 2002: [Coercion-Resistant Electronic Elections](https://eprint.iacr.org/2002/165.pdf)
==We define a scheme to be _coercion-resistant_ if it is infeasible for the adversary to determine if a coerced voter complies with the demands.==
We introduce a model for electronic election schemes that involves a more powerful adversary than previous work. In particular, **we allow the adversary to demand of coerced voters that they vote in a particular manner, abstain from voting, or even disclose their secret keys.**


**previous schemes** have required use of an u**ntappable channel throughout**. **Ours** only carries the much more practical requirement of an **anonymous channel during the casting of ballots, and an untappable channel during registration** (potentially using postal mail).
## 2016: [Improving the verifiability of the Estonian Internet Voting scheme](https://research.cyber.ee/~janwil/publ/ivxv-evoteid.pdf)
security analysis identified security requirements broadly divided into the categories of:
- **integrity**
- **confidentiality**
- **transparency**
- **coercion-resistance.**
==As a starting point of our analysis, we will use the attack tree presented by Heiberg and Willemson in 7.==

### Integrity
#### I-ballot box integrity
> [!Three direct attacks on the i-ballot box integrity can be identified:]
> 1. adding votes to the box
> 2. removing votes from the box
> 3. modifying votes already in the box

> [!The process of vote storage]
>  takes advantage of the Estonian PKI with digital signature capabilities and private keys stored on secure hardware tokens.
>  - VoteApp creates the digitally signed vote and sends it to the VFS
>  - VFS verifies the signature of the vote and forwards the vote to the VSS.
>  - VSS verifies the signature and acquires confirmation about the validity of the certificate to the signature from OCSP.
>  - VFS and VSS log the stages of processing both locally and to the LOG.

PKI usage allows us to assume that the stored votes are secured from the manipulations and that the eligibility of voters can be verified by the system. ==Unauthorized addition or modification of the votes would effectively require forging digital signatures.== However, there are **no comparable measures against the unauthorized removal of votes** from the i-ballot box.
**An attacker who wants to remove a vote from the system** has to compromise the VSS in a way that it would be possible to delete the corresponding file from storage
==Attackers must think of following risks:==
- certain window of time during which a vote can be verified by the individual verification tool.
	- If the vote is removed before the end of this window, there is a risk of detection.
- There are traces of vote storage in the log files on VFS, V S, LOG and OCSP.
	- If these traces are not removed and the logs are later correlated with the actual list of stored votes, there is a risk of detection.
-  **Potential detection by the individual verification tool can be easily prevented by deleting the vote after the verification window (30 or 60 minutes) has closed.**
- Tampering with the log files requires control – such as administrator access – over multiple components. the OCSP is hosted completely independently from the Internet voting system.
- **Currently the consistency of the VSS and OCSP views is not rigorously audited, which leaves the unauthorized removal of the votes from the i-ballot box a theoretical possibility.**

#### Tabulation integrity

> [!attacks on tabulation]
> 1. i-ballot box replacement
> 2. tabulation tool compromise
> 3. forgery of the voting result

> [!steps in the process of tabulating votes]
> - VSS verifies the signatures of the stored votes and extracts a set of encrypted votes sent to the tabulation.
> - TA takes the set of encrypted votes and decrypts them with the private key stored in the HSM.
> - TA aggregates and digitally signs the voting result.
> - Both VSS and TA log the status of each encrypted vote. These logs are later audited.

the **threat of actual forgery** of the voting result **has a valid countermeasure** as there exists an audit procedure, which involves retabulating the votes and comparing the result with the published one.

**An attacker wishing to replace the i-ballot box** before tabulation would have to compromise the VSS. Although the VSS is offline in this stage of the election, the same system is online during the voting period. This makes a **remote compromise possible** as well. ==A malicious VSS would simply replace the set of encrypted votes sent to tabulation. It would also use the forged set of encrypted votes as basis for audit log forgery.== 
There is a **==risk of detection for the attacker:==**
- it is possible to repeat the process of anonymization on the original set of signed votes using a different combination of hardware and software. **Currently this kind of audit has not been implemented.**
An attacker who has compromised the tabulation tool can take advantage of the fact that there is no way to either verify or audit if the encrypted ballots are decrypted correctly. **A flaw in the tabulation tool** – TA together with HSM – **could change the result without anyone noticing.**

==In the current scheme, the integrity of tabulation relies on the correctness of the software and hardware together with the integrity of the operating personnel==. If we want to **weaken the assumption that the central system is trustworthy and outsource aspects such as online vote collection to a third party,** ==additional countermeasures are required for both i-ballot box replacement and tabulation tool compromise.==

### Towards the solution
Recent research by Goggin et al. shows that the **margin of error of paper ballot counting** can be **reduced to about 1 . . . 2%, but not much lower**.
The corresponding solutions are generally known as providing ==end-to-end verifiability==, i.e. allowing to check that certain properties regarding the relationship of the stored ballots and the voting result actually hold.


> [!end-to-end verifiable voting]
> should provide the following properties:
> 1. **Cast as intended:** The voter is able to check that her ballot represents a vote for the candidate to whom she intended to give the vote.
> 2. **Well-formedness:** Anyone is able to check that valid ballots do not contain over-votes or negative votes.
> 3. **Recorded as cast:** The voter can check that her ballot is recorded as she cast it.
> 4. **Tallied as recorded:** Anyone is able to check that all the recorded ballots have been tallied correctly
> 5. **Consistency:** Anyone is able to check that the voters and the general public have the same view of the election records
> 6. **Authenticity/eligibility:** Anyone can check that any cast ballot has a corresponding voter who can perform check No. 3.


- Introducing an individual verifiability tool addressed **items 1 and 3** above
- These are also the two requirements that are targeted towards the voter herself and are hence relatively straightforward to implement.
- The remaining four requirements (often referred to as universal verifiability) refer to Anyone as a potential verifier.
	- The exact meaning of this term is vague. we need to make it clearer before actual implementation.

#### From observation to verification
The analogue of universal verification in the case of paper voting is the observation. **paper voting methods are designed such as voting in polling stations to protect the integrity of the voting result.** ==this procedure is carried out by human beings, there is room for mistakes== – so as to convince the general public in actual integrity, the ==observation is applied as a method.== Outsiders are allowed to participate and to observe the election procedures. **==observers help us to assure that the secure procedure for the voting method was correctly put into practice==**

Following the spirit of universal verifiability, we would like to think that ==observation is accessible to anybody==. **This is true in principle, but there are some limitations.**
- The first obstacle is technical.
	- **verifying statements concerning a digital ballot box or tally integrity assumes proficiency in cryptographic techniques**. In principle, anyone can achieve this, but in practice, not everyone does.
- The second obstacle involves the threat of coercion.
	- If everyone can get easy access to strong proof that her vote was tallied, this proof can be used to facilitate vote-selling.
There is also no universal access to the election data for the observers – for example, 
- lists of voters are out of bounds 
- only data about the observer herself can be viewed 
- the actual tabulation of the votes can only be observed.

The EVIV framework recently proposed by Joaquim et al. takes a very pragmatic approach towards universal verifiability.
In the election setup, votecasting and verification phases it explicitly relies on a set of designated trustees, e.g. for distributed key management and homomorphic tally computation. **EVIV uses homomorphic tallying, which has a remarkable performance overhead for large elections**

> [!kig på]
> we will be using provable decryption with mixing to provide vote privacy. However, the problem of verifying the proofs of decryption and mixing still remains, and we will solve it similarly to the EVIV by introducing the Data Auditor role and providing it with cryptographic integrity statements to verify.
> As with virtually all voting systems with an online component, the Estonian system also features **==a bulletin board==**. So far, the functionality of this bulletin board (called Vote Storage Server ) has been quite restricted, only allowing for limited-time individual verifiability. The second major goal of the current effort is to extend this functionality to also allow the Data Auditor to issue statements about the i-ballot box integrity.

### Proposed Scheme
- additional means will be added to verify that the voting result was tabulated correctly based on the votes that were collected and stored during the voting period.
	- a new role **==the Data Auditor==**  To perform this verification. will **verify the decryption proofs** exported during the vote decryption phase. this process must not violate the secrecy of the votes.
	- To enable flexible decryption proofs, the cryptosystem used for vote encryption, **RSA-OAEP  is replaced by a randomized homomorphic public-key algorithm**, e.g. ElGamal
		- This makes it possible to prove correct decryption while preserving privacy, ==using re-encryption mixnets such as [this](https://link.springer.com/chapter/10.1007/978-3-642-29011-4_17), [this](https://eprint.iacr.org/2015/1112) or [this](https://www.csc.kth.se/~dog/research/papers/TW10Conf.pdf)==
- to fix **i-ballot box integrity issues**, an extra commitment step will be added.
	- new party called the **==Registration Service==** will implement this. will essentially keep a ledger of the stored i-votes.
	- makes it **possible to outsource the duty of collecting votes** to a third party, as there is a **way to ensure that the integrity of the i-ballot box** is maintained.

==We take advantage of standard cryptographic primitives such as:==
- **the signature scheme** $σ = (Gen_{sig},Sign,Verify)$ with its key-generation, signing and verification functions
- **the randomized homomorphic public-key cryptosystem** $\epsilon = (Gen_{enc},Enc,Dec)$ with its key-generation, encryption and decryption functions.
- **the cryptographic hash-function** Hash.

> [!KIG PAAA]
> The Estonian Internet Voting scheme has been using three major components:
> 1. the Vote Forwarding Server
> 2. the Vote Storage Server
> 3. the Tabulation Application
>    
>    We propose a separation of duties. The Voting System is divided between:
>    1. the Election Organizer
>    2. the Vote Collector
>    3. the I-Ballot Box Processor
>    4. the Mixing Service
>    5. the Tallier
>    6. **Additional extra parties, that interact with the system:**
> 	   1. the Certification Authority
> 	   2. the Time-marking Service
> 	   3. the Registration Service
> 	   4. the Data Auditor(s)
> 	   5. the Voters

- Maaske brugbart
	- ![[Pasted image 20240302224007.png]]
	- ![[Pasted image 20240302224018.png]]
	- ![[Pasted image 20240302224026.png]]

#### 5.2 Voting stage
#TODO 
#### 5.3 Preparing the votes for tabulation
#TODO 
#### 5.4 Tabulating the voting result
#TODO 
#### 5.5 Auditing the election
#TODO 

### Discussion and conclussion
- Levels of auditing
- The role of mixing
- Outsourcing the vote collection
- End-to-end verifiability

#### Conclusion
This paper proposed several ==improvements to achieve the end-to-end verifiability of Estonian Internet voting.== 
> [!These were addressed:]
> - i-ballot box 
> - tabulation integrity 
> Previously, both of these aspects have relied heavily on human control and organizational measures.

The practical try-outs will give us a lot of information about the open issues, e.g. what kinds of conflicts may arise in practice between independent auditor organizations. Resolving these issues will give us a lot of work in future iterations.

A clear separation of roles and their duties opens up the opportunity to apply IVXV also in other elections, not just national elections in Estonia. Implementing this vision also remains a subject for future development.
## 2020: [How not to prove your election outcome](https://ieeexplore.ieee.org/document/9152765)
The Scytl/SwissPost ==e-voting solution was intended to provide complete verifiability== for Swiss government elections. **==We show failures in both individual verifiability and universal verifiability==** based on mistaken implementations of cryptographic components.
These failures allow for the construction of "proofs" of an accurate election outcome that pass verification though the votes have been manipulated. Using sophisticated cryptographic protocols without a proper consideration of what properties they offer, and under which conditions, can introduce **==opportunities for undetectable fraud even though the system appears to allow verification of the outcome==** .Our findings are immediately **relevant to systems in use in ==Switzerland== and ==Australia==, and probably also elsewhere.**

> [!sssssssss]
> **The incorrect use of sophisticated protocols such as** ==zero knowledge proofs (**ZKPs**==) and ==multiparty computation (**MPC**)== demonstrates pitfalls that potentially affect systems for applications other than voting. Many of the components have been proven secure elsewhere, but under assumptions that are not realised in this system

 Many of the components have been proven secure elsewhere, but under assumptions that are not realised in this system. **==We provide a short summary of the generalisable failures we observed:==**

> [!short summary of the failures observed]
> Many of the components have been proven secure elsewhere, but under assumptions that are not realised in this system
> 1) **Statically secure primitives are used in an adaptive setting**. The sVote system uses Maurer’s unified proofs framework ==[1]== for many of its ZKPs. These are proven to offer security in an interactive and static model (_i.e._ when the statement is given to the prover), but are used in sVote in a setting where the prover can choose the statement afterwards, thus making it vulnerable to the pitfall described in ==[2].==
> 2) **The facts proven in the ZKPs are not sufficient. A** ZKP proves a particular statement (or more precisely, membership of a specific language). But in sVote, the conjunction of the facts proven by the voting client is not sufficient to imply the desired properties about the votes.
> 3) **The multiparty protocol isn’t secure against collusion.** sVote uses an original multiparty protocol to compute the codes to be returned to voters. The protocol has five authorities and is intended to tolerate some dishonest participants. We show that one of them can misbehave alone (with a cheating client) and break verifiability.
> 4) **Hardness assumptions are not guaranteed.** Most of the protocols used in sVote rely on the hardness of some computational problems. For instance, in various places, it is expected that discrete logs of various group elements in various bases are unknown. However, sVote offers no evidence of how the group parameters and group elements are generated, which makes it impossible to verify whether a prover may know a trapdoor that would violate the specific instances of the computational problems used in the system. This can be used to violate both individual and universal verifiability in sVote.
> 
> **Every one of these errors allows a successful vote manipulation that passes verification, though in some cases it is informally clear that something has gone wrong.**


==We also provide a list of other cryptographic errors in OR proofs, hashing, _etc._, though they do not seem to lead to attacks.==

> [!main cryptographic aspects of sVote 2.1. (simplified)]
> The main components of the system are:
> - **A print office**, which generates and prints the code sheets, and is trusted.
> - **A voting client**, which is trusted for privacy only.
> - **A voting server**, which coordinates the server-side components of the election and is not trusted.
> - R**eturn codes control components (CCRs)**, among which one is assumed to be honest. 
> - **Mixing control components (CCMs)**, among which one is assumed to be honest.
> - **Auditors**, among which one is assumed to be honest.
> 
> These components have signing keys, which they use to authenticate (and log) their behavior, but we ignore them here.
### Cryptographic setup
The core of the cryptographic protocol happens in a group G of prime order q made of the quadratic residues modulo a 2048-bits prime _p =_ 2q + 1. The group parameters are chosen so that _g =_ 2 generates G.

**Before the election, each possible answer offered on a ballot** is assigned a small prime $v_i$ in G. **Each question on a ballot has at least three possible answers: yes, no, and blank**, though it may instead have several different candidates to choose from.

the system uses ==ElGamal encryption== over G. Each message is a small prime in G, or the product of such primes. All choices for a ballot are multiplied together, encrypted as a single ciphertext, and sent to the server.

So, whatever vote is cast, the number of small primes needed to represent the vote is fixed. The system expects that the product of all the _vi_ primes selected for any ballot will be smaller than _p._

ometimes El Gamal is used in its multi-element version. A public key is a tuple $(K^{(1)},K^{(2)},\dots,K^{(\psi)})$ where _ψ_ is the maximum number of questions on the ballot. The corresponding private key is the tuple of discrete logs of the public key, mod _p._ A message m, which is a tuple $(m_1,m_2,\dots,m_{\psi})$ of quadratic residues mod _p_, is encrypted by generating a random _r_ ∈ \[1], \[_q_] and setting the ciphertext to: $$E(m,r)=(g^r,m_1K^{(1)r},m_2K^{(2)r},\dots,m_{\psi}K^{(\psi)r}$$
The client sends both a vote ciphertext and a set of _partial Choice Codes_ that are used to compute the choice codes, along with a non-interactive ZKP that they are consistent—this is detailed below. The server-side has two roles: it first computes the choice codes for each voter and then, when all the votes have been received, it mixes and decrypts the votes.
This means there are three uses of non-interactive ZKPs:
1. the client uses three ZKPs to prove that the partial choice codes match the vote;
2. the server-side uses ZKPs to prove that the codes it returns match the partial choice codes submitted by the client;
3. the server-side uses ZKPs to prove that the complete list of votes is properly mixed and decrypted.

### Pitfalls of the Fiat-Shamir transform: why individual verifiability fails
**the vote validity NIZKPs are not sound, which can be used by a malicious client to submit a nonsense vote, prove it is valid, and retrieve the right choice codes.** The voter would then consider that her vote intent was correctly captured. However, when this vote was decrypted after being mixed, it would be invalid.

> [!Fiat-Shamir transform]
> **a standard method of turning an interactive proof into a non-interactive one**. Informally, the idea is simple: 
> - rather than waiting for the verifier to generate a random challenge, the prover generates a challenge by hashing the prover’s initial commitments. 
> - This can be proven to be secure assuming that the hash function behaves as a random oracle.

### The client-side proofs are not sufficient: why individual verifiability fails
**Even if the ZKPs were sound, individual verifiability would still fail because the ZKPs used to prove consistency between the vote codes and the vote are not sufficient.**
we show how this allows a cheating client to submit a ballot that substitutes a voter’s choice but states a corresponding _pCC_ that matches the voter’s request. This passes verification even if the NIZKPs are sound.

> [!The main problem]
>  The exponentiation proof $π_e$ in the vote generation proves that the _product_ of the partial choice codes has been correctly exponentiated—it does not prove that each individual element has been properly exponentiated.
#### Generating a proof of ballot validity when the choice codes do not match the vote
s
#### How will this be treated at the server side?
s
### Individual Verifiability: returning the right choice codes for a manipulated vote with server collusion
#### Faking correct choice return code generation
#### Does it pass verification?
### Picking Election Public Parameters: The use of TRAPDOOR commitments IN bayer-groth proofs and why the shuffle proof can be faked
#### Overview of this section: faking the shuffle proof
#### The soundness of the shuffle proof
### Discussion

> [!Ease of exploiting the problem] 
> T**he first attack requires knowing the randomness used to generate the vote ciphertexts that will be manipulated**. There are several ways this could be achieved. For example, an attacker could compromise the clients used for voting. Weak randomness generation (such as that which affected the Norwegian e-voting system) would allow the attack to be performed without explicit collusion.
> 
> **The second attack does not require any extra information at all, though it does rely on the election parameters having been set up in a particular way**. An easily-computed example set of trapdoored parameters is in Appendix B.

> [! Summary of the problem]
> This mixnet has a trapdoor - a malicious administrator or software provider for the mix could manipulate votes but produce a proof transcript that passes verification. Thus complete verifiability fails.

> [!Fixng the problem]
> The issue needs to be corrected by ensuring that the commitment parameters are generated in a way that prevents any entity from knowing the discrete logs—==concrete suggestions are contained in Section VIII==. Every verifier then needs to check the generation of the commitment parameters as well as the rest of the proof transcript.

to demonstrate one possible impact of the lack of soundness of this decryption proof, we exhibit an exploit in which a malicious authority (e.g., the $CCM_1$ of the system) modifies selected votes during the (partial) decryption procedure and forges decryption proofs that are indistinguishable from valid ones, and would therefore pass verification. This specific exploit has two limitations, but we do not rule out that there are other and possibly more dangerous ways of exploiting the same weakness.
1. In order to fake the decryption proof and also complete a valid proof of shuffle, the cheating _CCM_ needs to know the randomness used to encrypt the votes that it wants to modify. This can be accomplished by corrupting a voting client, or by a poor random number generator.
2. The cheating authority cannot declare an arbitrary false plaintext while also making the shuffle proof work. But it can, for any ciphertext, prove that it decrypts to something other than the truth. The exploit produces an output vote that will probably be nonsense rather than a valid vote.4 This exploit could then be used to political advantage to nullify only those votes with which the cheater disagreed.
#### Is this detectable or attributable to the cheating prover?
#### Producing a false decryption proof
#### The possibility to cheat and produce valid ballots.
### How do Others Pick their Public Parameters? How should they?
**One key issue that seems to have resulted in the problems we describe is the definition of the word** "**==independent.==**" when independent generators are required for the commitment scheme, the term means that the discrete log relation between them is unknown. In contrast, when discussing probability, the word independent means that probability does not change depending on the outcome of the others.
#### Common methods

#### Potential problems with these methods

#### In Practice
##### UniCrypt
##### Stadium
##### GRNET-Fauzi et al
##### CHVote prototype (2.0)
##### Verificatum
#### Conclusion and Recommendations
**Given that for most cases in e-voting it is possible to securely—and verifiably—generate independent generators without relying on multiparty computation, ==we recommend that this and only this should be done==.** We are impressed by the understanding and care taken by those researchers implementing e-voting libraries but concerned by the dangers still present by others using their libraries without understanding.
### Discussion/Conclusion
**Numerous serious issues** with the complete election verifiability process of the sVote 2.1 protocol open the way for undetectable electoral fraud. **Fake proofs are possible at almost every step**, from the client proving that the vote is valid, to the return of choice codes, to the mixing and decryption of the votes.

==In all cases, formally, verification would pass, though in some cases it would probably be observed that something unusual occurred (such as the presence of invalid votes).==

> [!Formal Proofs]
> formal proofs are not useless—they are important for clarifying assumptions and security claims, and they provide an argument (which can be checked) for why the system should be trusted. However, proofs themselves can be mistaken or insufficient. They should be required, but they are a part of the scrutiny process not a substitute for open scrutiny.

> [!Closing thoughts]
> We hope this work can help customers assess what does, and does not, constitute genuine verifiable computation. **==There is nothing gained by using a proven-secure component if its assumptions are not met in the context in which it is used==**==. Nor is there any advantage to sound ZKPs if they do not actually prove what is needed in the rest of the protocol.==
> 
> **==The aim of verifiable election software is verifiable election outcomes, not proofs that pass==**. **If the system itself does not come with meaningful evidence** that its verification procedure is sound, then an **apparently-successful verification implies nothing about the integrity of the election result.**


## 2019: [Breaking the encryption scheme of the Moscow Internet voting system](https://arxiv.org/abs/1908.05127)

> [!Hurtigt referat]
>  [Breaking the encryption scheme of the Moscow Internet voting system](https://arxiv.org/abs/1908.05127): We show **two successful attacks on the encryption scheme implemented in the voting system**
> 
> **The encryption used in this system is a variant of ElGamal over finite fields.** 
> - **In the first attack**
> 	- The used key sizes are too small. We explain how to retrieve the private keys from the public keys in a matter of minutes with easily available resources.
> -  After a fix, we found **the second attack**: 
> 	- The new implementation was not semantically secure. 
> 	- This newly found security vulnerability can be used for counting the number of votes cast for a candidate.


### What did we break?
As in many e-voting protocols, the encryption scheme is used to encrypt the choice of the voter to form an encrypted ballot. From the Javascript source code that is supposed to be run on the voting device of the voter, we deduce that the encrypted data consists solely of this choice (with no additional nonce or meta-data). It takes the form of a 32-bit unsigned integer called “deputy id” that looks random.
- The link between the deputy ids and the real names of the candidates is public, since the Javascript source code that must present the choices to the voters has to include it
**==Even if there is a strong trust assumption on the server that receives these votes, and even if it is honest and forgets the link between the voters and the ballots, there is still the issue of putting them in the blockchain for verifiability.==**

### The role of the blockchain in the protocol
**In the protocol, the encrypted ballots are sent to an Ethereum blockchain and stored as transactions, one transaction per ballot.** ==The argument for doing so is a typical one used in e-voting, namely offering the possibility for the voters to check that their vote is indeed taken into account.==
At the end of the election, again via the blockchain, the voters are also given a way to relate each encrypted ballot to the corresponding vote in cleartext. The goal is to provide the cast-as-intended property:
- if the voting client were to silently modify the choice of the voter, this would be detected

> [!BLOCKCHAIN STUFF MOSCOW]
> In the Moscow election, a specific, permissioned Ethereum blockchain was used. The impossibility for the nodes running this blockchain to rewrite the history of the ledger in order to remove a ballot after the voter has checked it, relies therefore on the assumption that enough nodes are honest. Furthermore, the access to this specific blockchain was not guaranteed to stay for long, and actually was cut by the organizers quickly after the election

#### To use or not to use a smart contract for decryption

> [!The original implementation]
> at the end of the election, the 3 private keys of the multilevel **ElGamal** were used to publicly decrypt all the ballots. This decryption was implemented in the **Solidity programming language**, to be run as part of a smart-contract by the nodes of the blockchain. The security properties that were sought by doing so are unclear. There are many ways to guarantee that a decryption has been correctly done, the most obvious in an **ElGamal** encryption setting is to include a simple zero-knowledge proof (as done for instance in **==Helios==**)

> [!The Second implementation]
> the protocol was changed, so that the decryption was done outside the smart-contract. The decryption results, namely the votes in clear, were uploaded to the blockchain as simple transactions with no computation. This operation occurs of course at the end of the election, in order to compute the tally. And additionally, the private key was also stored in the blockchain. This indeed allows the voters to verify that the decryption is correct.

> [!the purpose of the multilevel variant of ElGamal]
>  To compensate for this admittedly small key size. Maybe the designers hoped for a much better security by using the three successive encryptions, just like Triple-DES is much stronger than DES. Unfortunately, things are quite different for asymmetric cryptography. 
>  
>  Another cause of using 256-bit keys could be the confusion between the security brought by elliptic curve cryptography and the one offered by using finite fields.



> [!Lessons learned] 
> 1. Designers should be careful when using cryptography
> 2. Using a blockchain is not enough to guarantee full transparency
> 
> **ALSO**
> ==This is a good example of the difficulty for an Internet voting system to make the **vote secrecy rely uniquely on cutting the link between the voters and their encrypted ballots when they arrive on a server that should also authenticate the voters.**== What is really required is to cut the link with the vote in clear, and, for this, classical methods exist like homomorphic decryption or verifiable mixnets. In such a high-stakes election, many seemingly incompatible security properties must be satisfied (secrecy vs transparency), and advanced cryptographic tools are almost impossible to avoid.

## 2010: [Attacking and fixing Helios: An analysis of ballot secrecy](https://eprint.iacr.org/2010/625)


> [!Hurtigt referat] 
> - found a vulnerability in Helios 2.0 that can be used to violate privacy. Also present fix
> - demonstrate the practicality of the attack by violating a voter's privacy in a mock election
> - feasibility of an attack in the context of French legislative elections
> 	- constitutes a real threat to ballot secrecy
> - similar vulnerabilities in other electronic voting protocols, which do not assure ballot independence.
> 	- namely, the schemes by Lee et al., Sako & Kilian, and Schoenmakers 
> 
> **==independence and privacy properties are unrelated, and non-malleability is stronger than independence.==**

> [!Helios 2.0]
> an open-source web-based end-to-end verifiable electronic voting system, suitable for use in low-coercion environments.

 

> [!Vulnerability found]
> it allows an adversary to compromise the privacy of voters. 
> The vulnerability **exploits the absence of ballot independence** in Helios and works by **replaying a voter's ballot or a variant of it**, the replayed ballot magnifies the voter's contribution to the election outcome and this magnification **==can be used to violate privacy==**. 



## - 2018: [Voting: You Can’t Have Privacy without Individual Verifiability](https://inria.hal.science/hal-01858034/document)

> [!Seccurity goals]
> Electronic voting typically aims at **two main security goals**: 
> - **vote privacy**: no one should know how I voted;
> - **verifiability**. Verifiability typically includes:
> 	- **individual** verifiability (a voter can check that her ballot is counted);
> 	- **universal** verifiability (anyone can check that the result corresponds to the published ballots);
> 	- **eligibility** verifiability (only legitimate voters may vote). 
> 
> ==These two goals are often seen as antagonistic and some national agencies even impose a hierarchy between them: first privacy, and then verifiability as an additional feature.==



> [!WE show that]
> DER ER RIGTIGT MEGET BEVIS OG UNDERBYGGENDE BS
> actually, **privacy implies individual verifiability**. that is, guarantees that all the honest votes will be counted. In other words, systems without individual verifiability cannot achieve privacy (under the same trust assumptions). 
> - To demonstrate the generality of our result, we show this implication in two different settings
> 	- **cryptographic** and **symbolic** models, for standard notions of privacy and individual verifiability. Our findings also highlight limitations in existing privacy definitions in cryptographic settings.

## - 2020: [How to fake zero-knowledge proofs, again](https://inria.hal.science/hal-02928953/document)

> [!Hurtigt referat / main point]
> Zero-knowledge proofs are heavily used in e-voting protocols. A voter typically proves that her vote belongs to a set of valid choices and authorities show that they correctly decrypted the result. A standard way to move from an interactive proof to a non-interactive one is the Fiat-Shamir heuristic
> The Fiat-Shamir heuristic must be used with great care in zero-knowledge proofs. We explain how, in the Belenios voting system, while not using the weak version of Fiat-Shamir, there is still a gap that allows to fake a zero-knowledge proof in certain circumstances. Therefore **an attacker who corrupts the voting server and the decryption trustees could break ==verifiability==**

## 2019: [Belenios: a simple private and verifiable electronic voting system](https://inria.hal.science/hal-02066930/document)

> [!fra abstract]
> **We present the electronic voting protocol ==Belenios== together with its associated voting platform.**
> - Belenios guarantees vote privacy and full verifiability, even against a compromised voting server. 
> 	- It offers a good compromise between simplicity and security
> - We detail here the complete voting system from the setup to the tally and the recovery procedures. 
> - We comment on the use of Belenios in practice. In particular, we discuss the security choices made by election administrators w.r.t. the decryption key and the delegation of some setup tasks to the voting platform.

> [!Belenios explained]
> - Belenios is built upon Helios. 
> - Like in Helios, the voters can check that their ballots appear on the bulletin board, and that the result corresponds to the ballots on the board, while vote secrecy is guaranteed. 
> - In addition, Belenios provides eligibility verifiability: anyone can check that ballots come from legitimate voters, 
> 	- whereas in Helios, a dishonest bulletin board could add ballots without anyone noticing. Helios is thus vulnerable to ballot stuffing. 
> 	- **Eligibility verifiability can be added to voting systems through a signature mechanism and additional credentials**
> - like in Helios, Belenios is not coercion-resistant: voters may prove for whom they voted by providing the randomness used to produce their ballot or they may simply sell their voting material. Therefore Belenios should not be used in high stake elections.

> [!On E-voting]
> electronic voting systems still do not achieve an appropriate security level for high stake elections, such as politically binding national elections. At least, we believe that e-voting does not yet achieve the same level of security as paperbased elections, organized in physical polling stations, where people may watch the ballot box and manually count the ballots.

the code specification [26]

> [!Implementation and design decisions]
> - **Belenios involves several entities:** voters, of course, but also a registrar, and decryption trustees. None of these roles require special cryptographic skills. 
> - We therefore describe here which adaptions had to be made for our system to be usable. 
> - our voting platform offers **several levels of security**: 
> 	- the registration may be done directly by the voting server, 
> 	- the decryption key may or may not be split into several shares.
> -  **This yields different tradeoffs between security and simplicity**

## - 2022: [A privacy attack on the Swiss Post e-voting system](https://inria.hal.science/hal-03446801/file/rwc.pdf)

> [!Main point]
> how real world constraints led to shortcomings that allowed a privacy attack to be mounted. More precisely, dishonest authorities can learn the vote of several voters of their choice, without being detected, even when the requested threshold of honest authorities act as prescribed.
> 
> **==God, kort artikel==**, Indeholder:
> -  Protocol overview
> - Security goals
> - Description of attack

# Flere artikler 

- 2007: [Civitas: Toward a Secure Voting System](https://www.cs.cornell.edu/andru/papers/civitas-tr.pdf)
- 2015: [A comprehensive analysis of game-based ballot privacy definitions](https://eprint.iacr.org/2015/255.pdf)
- 2008: [Helios: Web-based Open-Audit Voting](https://www.usenix.org/legacy/events/sec08/tech/full_papers/adida/adida.pdf)
- 2013: [STAR-Vote: A Secure, Transparent, Auditable, and Reliable Voting System](https://www.usenix.org/system/files/conference/evtwote13/jets-0101-bell.pdf)
- 2016: [Voting System Security and Reliability Risks](https://www.brennancenter.org/sites/default/files/analysis/Fact_Sheet_Voting_System_Security.pdf)
- 2015: [A Study of Vulnerabilities in E-Voting System](https://www.researchgate.net/publication/315040247_A_Study_of_Vulnerabilities_in_E-Voting_System)
- 2020: [MIT researchers identify security vulnerabilities in voting app](https://news.mit.edu/2020/voting-voatz-app-hack-issues-0213)
- 2022: [Vulnerabilities Affecting Dominion Voting Systems ImageCast X](https://www.cisa.gov/news-events/ics-advisories/icsa-22-154-01)

==STOPPET HER==
- 2021/2022: Gitlab [E-voting documentation](https://gitlab.com/swisspost-evoting/e-voting/e-voting-documentation)
- 1987: [Verifiable Secret-Ballot Elections](https://cpsc.yale.edu/sites/default/files/files/tr561.pdf)
- 2018: [A Scheme for Three-way Secure and Verifiable E-Voting](https://www.computer.org/csdl/proceedings-article/aiccsa/2018/08612810/17D45WK5AmO)
- 2021: [Verifiable receipt-free electronic voting system based on mask ballot](https://www.computer.org/csdl/proceedings-article/isci/2021/004000a047/1Byed7IF4gU)
- 2020: [Ordinos: A Verifiable Tally-Hiding E-Voting System](https://www.computer.org/csdl/proceedings-article/euros&p/2020/508700a216/1oqKxJjEIUM)
- 2019/2023: [Towards End-to-End Verifiable Online Voting: Adding Verifiability to Established Voting Systems](https://www.computer.org/csdl/journal/tq/5555/01/10298802/1RADozid6p2)
- 2018: [SHARVOT: Secret SHARe-Based VOTing on the Blockchain](https://www.computer.org/csdl/proceedings-article/wetseb/2018/572601a030/13bd1fph1yP)
- 2018: [Alethea: A Provably Secure Random Sample Voting Protocol](https://www.computer.org/csdl/proceedings-article/csf/2018/668001a283/12OmNzZWbAn)
- 2022: [Efficient Homomorphic E-Voting Based On Batch Proof Techniques — An Improvement to Secure MPC Application](https://www.computer.org/csdl/proceedings-article/pst/2022/09851967/1FWmlodPyVO)

dunno, bachelorprojekt: [Investigating the Security of End-to-End and Blockchain-based Electronic Voting Systems](https://www.diva-portal.org/smash/get/diva2:1683763/FULLTEXT01.pdf)

* 2023: [The security of electronic voting: vulnerabilities and solutions](https://www.inria.fr/en/security-electronic-voting-digital-security-confidentiality)
- 2020: [A Survey on Feasibility and Suitability of Blockchain Techniques for the E-Voting Systems](https://arxiv.org/abs/2002.07175)
- 2012: [A conceptual approach to secure electronic elections based on patterns](https://www.sciencedirect.com/science/article/abs/pii/S0740624X12001360)
- 2004: [Building Secure Elections: E-Voting, Security, and Systems Theory](https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1540-6210.2004.00400.x)
- 2010: [Towards Trustworthy Elections](https://link.springer.com/book/10.1007/978-3-642-12980-3)
- 2004: [A secure electronic voting protocol for general elections](https://www.sciencedirect.com/science/article/abs/pii/S0167404804000276)
- 2005: [Coercion-resistant electronic elections](https://dl.acm.org/doi/abs/10.1145/1102199.1102213)
- 2010: [Security analysis of India's electronic voting machines](https://dl.acm.org/doi/abs/10.1145/1866307.1866309)
- 2009: [Security in Large-Scale Internet Elections: A Retrospective Analysis of Elections in Estonia, The Netherlands, and Switzerland](https://ieeexplore.ieee.org/abstract/document/5272405)
- 2012: [electronic elections security](https://books.google.dk/books?hl=en&lr=&id=d3bgBwAAQBAJ&oi=fnd&pg=PR7&dq=electronic+elections+security&ots=g7PRZEzHnx&sig=MR92_YGfO7gmJgL3R9advI3NiF8&redir_esc=y#v=onepage&q=electronic%20elections%20security&f=false) ([info](https://books.google.dk/books?id=d3bgBwAAQBAJ&dq=electronic+elections+security&lr=&source=gbs_navlinks_s))
- 2022: [Development of Electronic Elections Systems: A Review](https://pdfs.semanticscholar.org/7fe1/6ba303dcd6bf9c89fc0ebc3c19d15d7326ea.pdf)
- 2004: [A Security Analysis of the Secure Electronic Registration and Voting Experiment (SERVE)](https://www.cs.unibo.it/~babaoglu/courses/security11-12/resources/documents/serve.pdf)
- 2010: [Election Verifiability in Electronic Voting Protocols](https://link.springer.com/chapter/10.1007/978-3-642-15497-3_24)
- 2010: [electronic elections: The perils and Promises of Digital Democracy](https://books.google.dk/books?hl=en&lr=&id=OOhhIGSca7gC&oi=fnd&pg=PP1&dq=electronic+elections+security&ots=c7P-BSZgf4&sig=70lPhK7txTj4Ob0UEss9l032kRc&redir_esc=y#v=onepage&q=electronic%20elections%20security&f=false)
- 2010:  [Electronic Elections: A Balancing Act](https://link.springer.com/chapter/10.1007/978-3-642-12980-3_7)
- 2010: [Electronic Voting Security 10 Years after the Help America Vote Act](https://www.computer.org/csdl/magazine/sp/2012/05/msp2012050050/13rRUxNW1XL)
- 2007: [Towards secure online elections: models, primitives and open issues](https://www.inderscienceonline.com/doi/abs/10.1504/EG.2007.014161)
- 2004: [Electronic voting systems: security implications of the administrative workflow](https://ieeexplore.ieee.org/abstract/document/1232067)
- 2012: [Security and Elections](https://ieeexplore.ieee.org/abstract/document/6322973)
- 2023: [An Implementation and Analysis of Zero Knowledge Based E-Voting Solution With Proof of Vote on Public Ethereum Blockchain](https://www.computer.org/csdl/proceedings-article/metacom/2023/333300a423/1R1uwIFxK9i)
- 2023: [A Privacy-Preserving E-voting Scheme with Verifiable Format](https://www.computer.org/csdl/proceedings-article/dspp/2023/10404652/1TZNas84dsA)
- 2021: [Epoque: Practical End-to-End Verifiable Post-Quantum-Secure E-Voting](https://www.computer.org/csdl/proceedings-article/euros&p/2021/149100a272/1yg1eK2PSyA)
- 2023: [Election Verifiability with ProVerif](https://www.computer.org/csdl/proceedings-article/csf/2023/219200a488/1On91kycBXy)
- 2023: [Election Verifiability in Receipt-Free Voting Protocols](https://www.computer.org/csdl/proceedings-article/csf/2023/219200a063/1IUu2pu1iqQ)
- 2018: [Improving End-to-End Verifiable Voting Systems with Blockchain Technologies](https://www.computer.org/csdl/proceedings-article/ithings-greencom-cpscom-smartdata/2018/08726502/1axfgfdmNXO)



## 2007: [Civitas: Toward a Secure Voting System](https://www.cs.cornell.edu/andru/papers/civitas-tr.pdf)

> [!highlights fra abstract]
> - ==Civitas is the first electronic voting system that is==:
>  - **coercion-resistant**, 
>  - **universally and voter verifiable**, 
>  - **suitable for remote voting**. 
>  
>   This paper describes the design and implementation of Civitas. 
>   security proofs for design, information-flow security analysis for implementation. 
>   Evaluation of the tradeoffs between time, cost, and security.


> [!Developing Civitas led to several contributions:] 
> - A provably secure voter registration protocol, which distributes trust over a set of registration authorities.
> - A scalable design for vote storage that ensures integrity without expensive fault tolerance mechanisms.
> - A performance study demonstrating the scalability of secure tabulation.
> - A coercion-resistant construction for implementing a ranked voting method.
> - A concrete, publicly available specification of the cryptographic protocols required to implement a coercion-resistant, verifiable, remote voting scheme. This specification leverages many results in the cryptographic and voting literature.


> [!Requirements]
> **First**, in some circumstances, voters must register at least partly in person. 
> **Second**, voters must trust the computational device they use to submit votes
> 
> **Verifiability**. The final tally is verifiably correct. Each voter can check that their own vote is included in the tally (voter verifiability). Anyone can check that all votes cast are counted, that only authorized votes are counted, and that no votes are changed during counting (universal verifiability). ==for confidentiality==
> 
> **Coercion Resistance.** Voters cannot prove whether or how they voted, even if they can interact with the adversary while voting




> [!Threat model.] 
> **We require Civitas to be secure with respect to an adversary with the following capabilities:**
> - The adversary may corrupt a threshold of the election authorities, mutually distrusting agents who conduct an election. Agents might be humans, organizations, or software components.
> - The adversary may coerce voters, demand their secrets, and demand any behavior of them— remotely or in the physical presence of voters. But the adversary may not control a voter throughout an entire election, otherwise the voter could never register or vote.
> - The adversary may control all public channels on the network. However, we also assume the existence of some anonymous channels, on which the adversary cannot identify the sender, and some untappable channels, which the adversary cannot use at all.
> - The adversary may perform any polynomial-time computation.


> [!Civitas Architecture]
> ![[Pasted image 20240303030151.png]]


> [!Agents]
> five kinds of agents in the Civitas voting scheme: a **supervisor**, a **registrar**, **voters**, **registration tellers**, and **tabulation tellers**. Other than voters, all are elecion authorities:
> - The **supervisor** administers an election. This includes specifying the ballot design and the tellers, and starting and stopping the election
> - The **registrar** authorizes voters.
> - **Registration tellers** generate the credentials that voters use to cast their votes
> - **Tabulation tellers** tally votes.
> These agents use an underlying **==log service==** that implements publicly readable, insert-only storage.



> [!log service]
> Publicly readable, insert-only storage. Integrity of messages in a log is ensured by digital signatures. Agents may sign messages they insert, ensuring that the log service cannot forge new messages. The log service must sign its responses to reads, ensuring that attempts to present different views of log contents to different readers can be detected. Multiple instances of the log service are used in a single election. **==One instance, called the bulletin board==, is used by election authorities to record all the information needed for verifiability of the election. ==The remaining instances, called ballot boxes==, are used by voters to cast their votes.**


> [!NOTE] Other things of note
> - Descriptions and walkthrough of the different phases in the election
> - Security evaluation
> - Cryptographic components
> - secuirt proof
> - generelt bare gennemgang af opbygningen af systemet


> [!NOTE] trust assumptions
> 1. The adversary cannot simulate a voter during registration.
> 2. Each voter trusts at least one registration teller, and the channel from the voter to the voter’s trusted registration teller is untappable.
> 3. Voters trust their voting clients.
> 4. The channels on which voters cast their votes are anonymous.
> 5. At least one of the ballot boxes to which a voter submits his vote is correct
> 6. There exists at least one honest tabulation teller
> 7. **Nævnt senere:** The Decision Diffie-Hellman (DDH) and RSA assumptions hold, and SHA256 implements a random oracle.


> [!Attacks on election authorities.]
>  **Trust Assumptions 2, 5, and 6** allow all but one election authority of each kind to be corrupted. But certain attacks might still be mounted:
>  - A corrupt registration teller might fail to issue a valid credential share to a voter. The voter can detect this, but coercion resistance requires that the voter cannot prove that a share is valid or invalid to a third party. Defending against this could involve the voter and another election authority, perhaps an external auditor, jointly attempting to re-register the voter. The auditor could then attest to the misbehavior of a registration teller.
>  - The bulletin board might attempt to alter messages. But this is detectable since messages are signed. A bulletin board might also delete messages. This is an attack on availability, which is addressed in Section 11.
>  - A corrupt registrar might add fictitious voters or remove legitimate voters from the electoral roll. Each tabulation teller can defend against this by refusing to tabulate unless the electoral roll is correct according to some external policy.
>  - A corrupt supervisor might post an incorrect ballot design, stop an election early, or even attempt to simulate an election with only one real voter. Voters and tabulation tellers should cease to participate in the election once the supervisor exhibits such behavior.
>
>All election authorities might be simultaneously corrupted if they all run the same software. For example, an insider working at the software supplier might hide malicious code in the tabulation teller software. As discussed in Trust Assumption 6, this attack could violate coercion resistance, but it could not violate verifiability. To defend against insider attacks, election authorities should use diverse implementations of the Civitas protocols.

> [!Different Cryptographic voting schemes]
> **Cryptographic voting schemes can be divided into three categories, based on the technique used to anonymize votes**
> - **homomorphic encryption**, voters submit encrypted votes that are never decrypted. Rather, the submitted ciphertexts are combined (using some operation that commutes with encryption) to produce a single ciphertext containing the election tally, which is then decrypted.
> - **Blind signature schemes** split the election authority into an authenticator and tallier. The voter authenticates to the authenticator, presents a blinded vote, and obtains the authenticator’s signature on the blinded vote. The voter unblinds the signed vote and submits it via an anonymized channel to the tallier
> - **mix network schemes** voters authenticate and submit encrypted votes. Votes are anonymized using a mix, and anonymized votes are then decrypted. JCJ and Civitas are both based on mix networks

> [!Andre Pointer]
> - [Smith](https://rangevoting.org/WarrenSmithPages/homepage/crirv.pdf) proposes implementations of single transferrable vote (STV) and range voting that defend against Italian attacks(**Coercion**). [Heather](https://dl.acm.org/doi/10.1109/CSF.2007.22) proposes an implementation of STV for Pretˆ a Voter.
> - Finally, a report on the security of a real-world remote voting system, [SERVE, identifies a number of open problems in electronic voting](https://www.acm.org/binaries/content/assets/public-policy/usacm/e-voting/reports-and-white-papers/serve_report_full_paper.pdf)**These problems include**: 
> 	- transparency of voter clients, 
> 	- vulnerability of voter clients to malware, 
> 	- vulnerability of the ballot boxes to denial-of-service attacks that could lead to large-scale or selective disenfranchisement.

## 2015: [A comprehensive analysis of game-based ballot privacy definitions](https://eprint.iacr.org/2015/255.pdf)
We survey game-based security definitions for the privacy of voting schemes. In addition to known limitations,  several previously unnoticed shortcomings are found. 
conclusion: none of the existing definitions is satisfactory. they either provide only weak guarantees, or can be applied only to a limited class of schemes, or both.

we propose a new game-based definition of privacy which we call BPRIV. also identify a new property which we call strong consistency, needed to express that tallying does not leak sensitive information
## 2008: [Helios: Web-based Open-Audit Voting](https://www.usenix.org/legacy/events/sec08/tech/full_papers/adida/adida.pdf)

> [!NOTE] Fra [A comprehensive analysis of game-based ballot privacy definitions](https://eprint.iacr.org/2015/255.pdf)
> We have shown that BPRIV can indeed be realized by a real-scale protocol, namely Helios [4]. Since Helios satisfies BPRIV and is strongly consistent, it immediately follows that Helios is secure for a simulation-based notion of privacy

> [!Sales pitch]
> Voting with cryptographic auditing, sometimes called open-audit voting, has remained, for the most part, a theoretical endeavor.
> 
> We present Helios, the first web-based, open-audit voting system. Helios is publicly accessible today: anyone can create and run an election, and any willing observer can audit the entire process. Helios is ideal for online software communities, local clubs, student government, and other environments where trustworthy, secretballot elections are required but coercion is not a serious concern. With Helios, we hope to expose many to the power of open-audit elections.

==God gennemgang af hvordan det fungerer==

## 2012: [E-voting System Using Homomorphic Encryption and Blockchain Technology to Encrypt Voter Data](https://arxiv.org/pdf/2111.05096.pdf)


> [!abstract] 
> Homomorphic encryption and blockchain technology are regarded as two significant technologies for improving e-voting systems. In this paper, we suggest a novel e-voting system using homomorphic encryption and blockchain technology that is focused on encrypting voter data. By encrypting voter information rather than cast votes, the system enables various statistical analyses regarding the vote result while securing the credibility, privacy and verifiability of overall e-voting system. We checked the efficiency of the overall system by comparing the speed of the proposed system with the speed of other e-voting systems that use homomorphic encryption and blockchain technology.
> 
> 
> **==Homomorphic encryption guarantees ballot verifiability and result verifiability== of votes while the ==blockchain technology promises integrity and transparency==**
> 
> **==WEAKNESS:==** voters cannot be certain that the cast votes are the same as the encrypted forms, Because the cast votes are encrypted in the form of a cipher text.


> [!Blockchain] 
> Blockchain is a distributed and decentralized public ledger managed by a peer-to-peer network. Once the data in one block undergoes change, the revision process is recorded and shared by all the other blocks in the blockchain system. In other words, it is impossible to amend the data secretly. This is a clear advantage in an e-voting system because blockchain itself can monitor whether the voting results are manipulated by external forces. Any forced revision of data is detected immediately. The transparency of a blockchain network leads to credibility of the total e-voting system. Moreover, the main characteristic of blockchain system, especially public blockchain, is that its network is decentralized. Decentralized networks avoid reliance on any central authority; decisions for the total system are made by a majority of the members in the network. Decentralization of blockchain networks can prevent any possible corruption of total e-voting systems created by central authorities.


> [!Homomorphic Encryption]
> [Homomorphic encryption](https://crypto.stanford.edu/craig/craig-thesis.pdf) is a cryptographic technique that enables computations of encrypted data. To be precise, the result of computing encrypted data is equal to the result of encrypting the computation of plain data.
> . In order to compute encrypted data without using homomorphic encryption, encrypted data must undergo decryption; this process creates a risk of exposing plain data and weakens the overall security of the database. Thus, homomorphic encryption guarantees data security by eliminating the need to send plain data
> - has weaknesses that hinder practical implementation
> 	- Data that deploys homomorphic encryption cannot help but require large capacity
> 	- speed of encrypting plain data and of computing encrypted data are not fast enough to be practical
> 	- The accuracy of homomorphic encryption for large-scale data is also in doubt because the noise, that occurs with every computation, eventually becomes too large to ignore.


> [!E-voting and the blockchain]
> Because the transparency and detectability of a decentralized blockchain network become strengths in an e-voting system, there have been several trials to implement blockchain technology in an e-voting system:
> -  [Secure voting system using ethereum’s blockchain](https://scholarworks.boisestate.edu/cgi/viewcontent.cgi?article=1174&context=cs_facpubs#:~:text=In%20this%20paper%2C%20we%20propose,secure%2C%20and%20cost%2Deffective.&text=contracts%20to%20achieve%20voter%20administration%20and%20auditable%20voting%20records.)
> - [Blockchain based e-voting recording system design](https://ieeexplore.ieee.org/document/8272896)
> - [Blockchain-Based E-Voting System](https://www.researchgate.net/publication/327812253_Blockchain-Based_E-Voting_System)
> - [Secure digital voting system based on blockchain technology](https://repository.uwl.ac.uk/id/eprint/4510/1/Secure%20Digital%20Voting%20System%20based%20on%20Blockchain%20Technology%20-%20IGI%20Global%20e-Gov-for%20repo.pdf)
> - [An e-voting protocol based on blockchain](https://eprint.iacr.org/2017/1043.pdf)
> - [Large-scale election based on blockchain](https://www.sciencedirect.com/science/article/pii/S1877050918302874)
> - [An e-voting system based on blockchain and ring signature](https://dgalindo.es/mscprojects/yifan.pdf)
> 
>Two in particular, [Secure voting system using ethereum’s blockchain](https://scholarworks.boisestate.edu/cgi/viewcontent.cgi?article=1174&context=cs_facpubs#:~:text=In%20this%20paper%2C%20we%20propose,secure%2C%20and%20cost%2Deffective.&text=contracts%20to%20achieve%20voter%20administration%20and%20auditable%20voting%20records.) and [An e-voting system based on blockchain and ring signature](https://dgalindo.es/mscprojects/yifan.pdf), introduced e-voting systems using blockchain and a ring signature.
> **E-voting systems based on blockchain technology might have difficulty in preserving end-to-end privacy** cryptographic techniques, such as homomorphic encryption, ring signature, and blind signature, can ensure that a blockchain-based e-voting system is able to preserve the privacy of voters ([Privacy and verifiability in voting systems: Methods, developments and trends](https://www.sciencedirect.com/science/article/pii/S1574013713000282))
> In particular, [Large-scale election based on blockchain](https://www.sciencedirect.com/science/article/pii/S1877050918302874) introduces a new e-voting system that uses blockchain and a ring signature. **The uniqueness of this e-voting system is that it enables large-scale elections, unlike other blockchain-based e-voting systems.**

## 2013: [Privacy and verifiability in voting systems: Methods, developments and trends](https://www.sciencedirect.com/science/article/abs/pii/S1574013713000282)

> [!Point of article]
> The multitude of notions, primitives and proposed solutions that claim to achieve both privacy and verifiability form an interesting but complex landscape. The purpose of this paper is to survey this landscape by providing an overview of the methods, developments and current trends regarding privacy and verifiability in voting systems.

## 2013: [STAR-Vote: A Secure, Transparent, Auditable, and Reliable Voting System](https://www.usenix.org/system/files/conference/evtwote13/jets-0101-bell.pdf)
## 2016: [Voting System Security and Reliability Risks](https://www.brennancenter.org/sites/default/files/analysis/Fact_Sheet_Voting_System_Security.pdf)
## 2015: [A Study of Vulnerabilities in E-Voting System](https://www.researchgate.net/publication/315040247_A_Study_of_Vulnerabilities_in_E-Voting_System)
## 2020: [MIT researchers identify security vulnerabilities in voting app](https://news.mit.edu/2020/voting-voatz-app-hack-issues-0213)
## 2022: [Vulnerabilities Affecting Dominion Voting Systems ImageCast X](https://www.cisa.gov/news-events/ics-advisories/icsa-22-154-01)


## [Cryptography meets voting](https://www.hit.bme.hu/~buttyan/courses/BMEVIHI5316/Smith.Crypto_meets_voting.pdf)
asdasdasdddddddddddddd


## [Three Voting Protocols: ThreeBallot, VAV, and Twin](https://www.usenix.org/legacy/event/evt07/tech/full_papers/rivest/rivest_html/index.html)
