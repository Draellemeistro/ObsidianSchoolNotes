earlier  [[Questions - Industrial IoT]] next [[Questions - IoT and Cloud-Edge Computing]]
## What is the difference between typical [[IoT device]] and [[standard wireless devices]]? 
- Different roles and capabilities (simpler functions, like sensing, actuation. Often focused on specific functions, instead of more general)

**They're more limited in their scope of functionality.** Often comparatively lower processing power. Also lack of software updates (or very rare updates)
- **Main goals:** <span style="color:rgb(255, 0, 0)">Low cost</span>, and very specific (_stringent_) requirements on <span style="font-weight:bold; color:rgb(255, 0, 0)">energy consumption</span> 
	- **Balanced with** life-cycle, precision, reliability

**Embedded devices.** Often inaccessible and irreparable, such as in buildings or cars.
Should be <span style="color:rgb(255, 0, 0)">deployed by projecting long-term future ise</span>
######  [[IoT device-Power Consumption|Power Consumption]]
Battery may not be rechargeable, while operational time should be more than 10 yrs (_example_)

### What are the basic tasks that a typical [[IoT device]] performs and their relative [[IoT device-Power Consumption|power consumptions]]? 
- Sensing (Can be active, or passive)
- Computation
- Communication (<span style="font-weight:bold; color:rgb(255, 0, 0)">The hungry one</span>)
	- - The difference between transmission and reception is <span style="font-style:italic; color:rgb(255, 0, 0)">small</span>
	- 
### What is the basic [[Duty cycle and Battery energy|strategy to reduce energy consumption]] of a typical IoT device? 
##### <span style="color:rgb(255, 0, 0)">Make devices sleep!</span>
[[IoT device-duty-cycle|Duty cycle]] (activity factor) has to be very low in energy-constrained devices if long lifetime is required
- A device wakes-up when required (periodically, triggered by some external event)
- senses, computes, communicates,
- back to sleep 

## Sketch a general structure of an [[IoT network]]. 
see also [[IoT access networks]]  -- [[IoT Networking technologies]]
### Elaborate on a general classification of IoT networks and provide examples of technologies.
[[Short-range Networks]] -- [[Long-range low-power IoT Networks]] ???
## What are general characteristics of [[IoT traffic]] with respect to the standard types of IoT applications? 
**Depends on application.** Often many short packets. 
- <span style="color:rgb(255, 0, 0)">predominantly</span> **uplink** <span style="color:rgb(255, 0, 0)">oriented (_sensors send readings to.....)</span>
	-  (... [[Push-based reporting]]??) when devices initiate reporting
	- [[Pull-based reporting]] when devices are queried (**ASKED**) for readings
- **Downlink** <span style="color:rgb(255, 0, 0)">is mainly used for signaling and network-control functions</span> 
	- may also carry data in scenarios with <span style="color:rgb(255, 0, 0)">actuation</span>
- **CLASSES:** [[Full-buffer reporting]] and **[[Intermittent reporting]]** (<span style="color:rgb(255, 0, 0)">typically this</span>)
- <span style="font-weight:bold; color:rgb(255, 0, 0)">intermittent:</span> 
	- [[Real-time control]] (<span style="color:rgb(255, 0, 0)">often seen in</span> [[Industrial IoT]])
		- <span style="color:rgb(255, 0, 0)">Easy to deal with scheduling</span> <span style="font-weight:bold; color:rgb(255, 0, 0)">(STATIC SCHEDULING)</span>
		- Isochronous communications: devices have to be tightly synchronized
		- **Extreme reliability-latency requirements**
	- [[Periodic Monitoring]]
		- Devices continuously observe the environment
		- reporting is performed in (quasi)regular periods
		- **Lower reliability requirements**
	- [[Event Detection]] (ex: alarm the user about some event)
		- Devices continuously observe the environment
		- if observed values (or _event_) reach threshold, report
		- high reliability requirement

### Elaborate on the differences between [[Asynchronous Arrivals|asynchronous]] and [[Synchronous Arrivals|synchronous]]  in [[IoT traffic generation models|traffic generation]].
[[asynchronous communication]] 
![[image_IoT traffic 1.png]]
![[image_Questions - Introduction to IoT.png]]
##### <span style="color:rgb(255, 192, 0)">Async</span> 
aggregated over devices shows stable (stationary behavior). no synchronism between the reporting devices. **Models periodic reporting**
<span style="color:rgb(255, 0, 0)">Makes it easier to dimension the network</span>
##### <span style="color:rgb(255, 192, 0)">Sync</span>
Users’ traffic arrivals are independent of each other and independent of their previous traffic arrivals. **Models [[Event Detection]] reporting**.... 
<span style="color:rgb(255, 0, 0)">Very stressful for network, hard to cope with</span>