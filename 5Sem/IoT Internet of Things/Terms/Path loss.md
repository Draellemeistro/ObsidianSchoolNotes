**Wireless receivers are characterized with a minimum required
received power in order to actually receive signal**
(_So-called receiver sensitivity_)

- Path loss is a rough approximation of the attenuation of the wireless channel
	- Depends only on the distance
	- easy to use deterministic model
	- in principle, not very accurate (Just describes free space propagation)


- Typical example:
	- $P_{T}=3\text{ dBm}$
	- minimum $P_{R}=-101\text{ dBm}=RS\text{ (receiver sensitivity)}$
- If the received power is below the receiver sensitivity, reception is not possible
	- Received power depends on the transmitted power and power loss during transmission
- the basic [[Path loss]] model is given by:
$$P_{L}=K {({\frac{d}{d_{0}}})}^{\alpha}$$
- $\alpha$ os the path-loss exponent
	- depends on the environment
	- In principle, less obstacles (natural, man mande) implies lower $\alpha$
- $K$ is constant
	- May depend on e.g., frequency
- **this path loss in dBs is:**
	- $P_{L}[dB]=10\log_{10}K+10\alpha \log_{10} ({\frac{d}{d_{0}}})$
	- **at $d = d_{0}$** 
		- $P_{L}[dB]=10\alpha \log_{10}K$
		  
	- ![[image_Path loss-1.png]]

**[[Path loss]]:** Depends on frequency, weather conditions, day/night
![[image_Path loss.png]]
- Transmitted power $P_T$ \[dBm\]
- Received power $P_R$ \[dBm\]
- Path loss $P_L$ \[dB\]
- $P_T[dBm]=10\log_{10}\frac{P_{T}[W]}{1 \text{ mW}}$
- **Example:**
	- $P_{T}[W]=1 \to P_{T}[\text{dBm}]=30$
- $P_{R}[\text{dBm}]=P_{T}[\text{dBm}]-P_{L}[\text{dB}]$



- Path loss is a rough approximation of the attenuation of the wireless channel
	- Depends only on the distance
	- easy to use deterministic model
	- in principle, not very accurate (Just describes free space propagation)

- According to path loss model, there is critical distance **𝑟** after which the signal becomes too week to be received
	- Before $r$, the signal is received for sure
		- **not very realistic**
	- ![[image_Path loss-2.png]]


#### Three basic phenomena related to wireless propagation
- **[[Path loss]]:** Depends on frequency, weather conditions, day/night
- **[[Shadowing]], Shadow fading:** Slow variations in received power due to obstacles on the propagation path
- **[[Fading]]:** Fastter variations in received power (faster than [[Shadowing]])
	- Consequence of multipath (i.e., interference among the multiple components of the wave at the point of reception)
	- time and frequency dependent
![[image_Shadowing-3.png]]