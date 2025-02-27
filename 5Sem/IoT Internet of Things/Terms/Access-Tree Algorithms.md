Made specifically with the [[Star Topology]] in mind. **[[Star Topology]] is typically what we have in [[IoT access networks]]**
> [!fail] A lot of variants and a lot of nice theory, **BUT mostly of academic interest**

- $n$ users, experiencing packet arrivals
- A single, common access point (PA)
- Slotted time on the shared link
### The main idea
Collision-resolution through (random) splitting of the colliding users driven by the feedback broadcasted from the receiver
![[image_Access-Tree Algorithms.png]]

## [[Binary tree algorithm (BTA)]]
- All users with packets transmit in the first slot
- If the slot is a collision slot, the collision- resolution procedure starts:
- The users are instructed via feedback to split into 2 groups
- The users choose the group randomly
- The users from the “first” group transmit in the next slot, the others wait
- The splitting procedure repeats until a singleton slot happens, after which the users from the next group in line transmit…
- ![[image_Access-Tree Algorithms-1.png]]
