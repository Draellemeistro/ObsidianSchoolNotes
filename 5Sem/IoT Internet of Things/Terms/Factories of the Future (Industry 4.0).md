## Service requirements for cyber-physical control applications in vertical domains (TS 22.104)
from [[5G-Service Requirements]]
#### Examples of use-cases:
###### [[Factories of the Future (Industry 4.0)]]
- [[Motion control]]
- factory automation
- [[Process Automation (PA) (batch processing)]]
- automated guided vehicles
- ....


### [[Motion control]]
![[image_5G-Service Requirements.png]]
##### Closed-loop control in industrial setups
- A multitude of sensors/actuators controlled by a single controller
	- Actuators are typically machines with moving parts
		- risk to the personnel and the production process
###### Controllers periodically communicate with sensors and actuators:
- Transaction: sensing $\to$ control $\to$ actuation
	- isochronous operation
- exchanged messages are small
	- couple of tens of bytes maximum

### [[Process Automation (PA) (batch processing)|Process Automation]]

> [!NOTE] **Production of goods in bulk quantities, like chemicals, liquids, reactive gasses etc**
> - Closed loop control
> - Monitoring
> - [[Motion control]] is of no or limited importance
> 
> 

#### **Closed-loop control**
![[image_Process Automation (PA) (batch processing).png]]
#### **Process and asset monitoring**
![[image_Process Automation (PA) (batch processing)-1.png]]
- **use case 1:** Sensors generating periodic measurements of a continuous value (temperature, pressure, flow rate sensors)
- **use case 2:** Sensors generating waveform measurements (vibration sensors)
- **use case 3:** Cameras (regular or thermal) for asset monitoring