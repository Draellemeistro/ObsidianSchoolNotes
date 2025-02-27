# Network core: packet/circuit switching, internet structure
## The network core:
- mesh of interconnected routers
- **packet-switching**: hosts break application-layer messages into **packets**
	- network forwards packets from one router to the next, across links on path from source to destination
## Two key network-core functions
![[Pasted image 20240208142123.png]]
#### Forwarding aka '*switching*'
**local action**: move arriving packets from router’s input link to appropriate router output link
#### Routing
**global action**: determine sourcedestination paths taken by packets
routing algorithms

## Packet-switching: 
### store-and-forward
![[Pasted image 20240208142432.png]]
- **packet transmission delay**: takes L/R seconds to transmit (push out) L-bit packet into link at R bps
- **store and forward**: entire packet must arrive at router before it can be transmitted on next link

> [!One-hop numerical example:]
> - L = 10 Kbits
> - R = 100 Mbps
> - one-hop transmission delay = 0.1 msec

### queueing
![[Pasted image 20240208142525.png]]
Queueing occurs when work arrives faster than it can be serviced
**Packet queuing and loss**: if arrival rate (in bps) to link exceeds transmission rate (bps) of link for some period of time:
- packets will queue, waiting to be transmitted on output link
- packets can be dropped (lost) if memory (buffer) in router fills up
## circuit switching:
### Alternative to packet switching
end-end resources allocated to, reserved for “call” between source and destination
- in diagram, each link has four circuits.
	- call gets 2nd circuit in top link and 1st circuit in right link
- dedicated resources: no sharing
	- circuit-like (guaranteed) performance
- circuit segment idle if not used by call (no sharing)
- commonly used in traditional telephone networks
![[Pasted image 20240208142836.png]]
### FDM and TDM
#### [[frequency division multiplexing (FDM)]]
- optical, electromagnetic frequencies divided into (narrow) frequency bands
- each call allocated its own band, can transmit at max rate of that narrow band
![[Pasted image 20240208143110.png]]
#### [[Time Division Multiplexing (TDM)]]
- time divided into slots
- each call allocated periodic slot(s), can transmit at maximum rate of (wider) frequency band (only) during its time slot(s)
![[Pasted image 20240208143140.png]]
## Packet switching versus circuit switching
