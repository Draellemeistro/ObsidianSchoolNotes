> [!NOTE] Narrow Band IoT (NB-IoT)

### Main features
- Thousands of devices per base station (\~50K)
- Low energy consumption (> 10yrs battery life)
- Deep indoor penetration (164 dBm MCL)
- Low cost (\~5 USD per [[NB-IoT]] radio module)
- low data volume (few transmissions per day)
- latency is not critical
- plug and paly (no gateways)
- **no mobility supported!**
- Worldwide standard
### Some remarks
- NB-IoT achieves cost reduction and improved power efficiency wrt LTE
	- Less complex RF-front-end
	- Lower bandwidth
	- Lower data rates
- NB-IoT basically inherit the access networking mechanisms from LTE
	- **Not really IoT friendly**

![[image_NB-IoT.png]]
![[image_NB-IoT-1.png]]
# NB-IoT deployment options
![[image_NB-IoT-2.png]]
![[image_NB-IoT-3.png]]
![[image_NB-IoT-4.png]]
## NB-IoT coverage enhancement
> [!NOTE] Coverage enhancement is achieved by repetitions of the packets!
### NB-IoT Supports 3 Coverage Enhancement Levels
![[image_NB-IoT-5.png]]
##### CE-Level 0 – Equivalent to GSM coverage (RSRP>-114 dBm)
##### CE-Level 1 – 10 dB gain over GSM (RSRP > -124 dBm)
##### CE-Level 2 – 20 dB gain over GSM (RSRP < -124 dBm)

# [[SODAQ NB-IoT Arduino]]
