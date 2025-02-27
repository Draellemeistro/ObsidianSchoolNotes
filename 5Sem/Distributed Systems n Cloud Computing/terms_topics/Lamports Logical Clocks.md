#  asdads

# asdasd

## Lamports Scalar-Based Logical Clocks
- [[Logical Clocks]] $C:E\to T$, $E$ event set, $T$ set of time stamps
	- Clock condition: $\text{if }a\to b$ then $C(a)\to C(b)$

Local logic clocks
- of a,b in same process i and $a\to b$, then $C_{i}(a)<C_{i}(b)$
- process $i$ sends message that event a happened, that is reeived y process $j:C_{i}(a) < C_{j}(b)$
	- **note the i and j**

**Introduce a counter in each component!:** $C_{i}$ in component $i$
	- **Internal event:** increment C_i before executing the event
	- component i sends message to component j including the value of C_i : Tm = C_i
	- upon receival component j sets its own clock to c_j = max(C_j , Tm) + 1

**Scalar clocks are necessarily striclty consistent.**
	- For every two events a and b happening both in process i, and C(x) being the timestamp for each x, it is necessary that $C(a)\neq C(b)$!
![[image_Lamports Logical Clocks.png]]
![[image_Lamports Logical Clocks-1.png]]

### Limitations

> [!NOTE]
> ![[image_Lamports Logical Clocks-2.png]]
> C(Tx(m1))<C(Tx(m2))
> But can we say that the transmission of m2 depend on the transmission of m1?
> 

> [!NOTE] Causality is not captured! if $C(a) < C(b)$ that a *causally preceded* b
> **Solution:** [[Vector Clocks]]

