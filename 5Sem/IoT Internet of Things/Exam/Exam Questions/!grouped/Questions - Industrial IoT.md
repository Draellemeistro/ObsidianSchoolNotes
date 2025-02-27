**earlier:** [[Questions - General IoT Standards and Technologies]], **next:** [[Questions - Introduction to IoT]]
## **(1)** State the difference between [[IoT]] and [[Industrial IoT]]. 
IoT ---- [[Internet of Things]] / [[IoT]] / [[consumer IoT]]
IIoT --- [[IIoT]] / [[Industrial IoT]] 
[[IIoT and IoT]]

- IoT is mainly applied to consumer applications (**ex:** home automation, wearables) 
- **[[Industrial IoT]] (IIoT)** Is the application of IoT within the industrial sector
- Data collection, connectivity and security are common <span style="font-weight:bold; color:rgb(255, 192, 0)">features of IoT and IIoT</span>

### State a couple of applications of each technology.
##### [[IIoT Applications]]
Industrial applications are typically divided into:
- **[[Process Automation (PA) (batch processing)]]**
	- Monitoring and control of continuous flow (process)
	- **Examples:** chemical manufacturing, pulp & paper, oil & gas, etc....
- **[[Factory automation (FA) (discrete automation)]]**
	- Perform discrete control over subtasks
	- **Examples:** Electronics, cars
![[image_Industrial IoT-2.png]]

### Define the six [[ISA traffic classes|traffic classes]] in [[Industrial automation]] according to ISA. State an example of each class.
##### <span style="color:rgb(255, 0, 0)">3 categories</span>
| CATEGORY | CLASS | APPLICATION | LATENCY | CRITICAL LEVEL |
| -------- | ----- | ----------- | ------- | -------------- |
###### 1. Safety
| **safety** | 0   | -  Emergency shutdowm<br>-  Automatic fire control | 10-250 _ms_ | Always Critical |
| ---------- | --- | -------------------------------------------------- | ----------- | --------------- |
###### 2. control
| **control** | 1     | Closed loop regularity  | 10-500 _ms_ | often critical       |
| ----------- | ----- | ----------------------- | ----------- | -------------------- |
| **control** | **2** | Closed loop supervisory | 10-500 _ms_ | usually non-critical |
| **control** | **3** | Open loop control       | 10-500 _ms_ | non-critical         |
###### 3. monitoring
| **monitoring** | 4     | Alerting                            | sec-days | non-critical |
| -------------- | ----- | ----------------------------------- | -------- | ------------ |
| **monitoring** | **5** | Logging and downloading / uploading | sec-days | non-critical |
##### <span style="color:rgb(255, 0, 0)">Examples</span>


##### [[Industrial Communication]]
- **Communication/networking** is the backbone of all [[Industrial automation]] components for efficient production systems
- Communication between devices and controllers were originally based on **wired connections**
- First generation of industrial communication networks were built on a variety of serial-based protocols