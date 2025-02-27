1. **Typical for IoT**
2. Different types
	1. Real-time control ([[Industrial IoT]])
	2. Periodic monitoring
	3. Event detection

### [[Real-time control]]
- Deterministic sensing-control-actuation cycles
- Easy to deal with in terms of scheduling
	- Static scheduling
- Isochronous communications
	- All devices have to be tightly synchronized
		- i.e., should have the same absolute time references
- Extreme reliability-latency requirements
	- Short cycle times - 1 ms
		- communication latency 0.1 ms
		- reliability $1-10^{-6}$

### [[Periodic Monitoring]]
- Devices continuously observe the environment
- reporting is performed in (quasi)regular periods
- Periodicity depends on application
	- tens of milliseconds ([[Industrial automation]]) to hours (electricity consumption)
- Lower reliability requirements
	- 0.95 - 0.99

### [[Event Detection]]
- Typical purpose is to alarm the user about some event
- Devices continuously observe the environment
- Reporting is performed only if the value(s) of the observed parameter(s) cross predefined threshold
	- e.g., data is generated only upon detection of some prespecified event
- high reliability requirement
- **examples:**
	- temperature becomes too high
	- Concentration of some gasses becomes too high
	- Detection of a movement
