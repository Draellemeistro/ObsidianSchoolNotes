**An [[IoT device]] Performs  three basic tasks:**
- Observes its surroundings (**sensing**) [[IoT-Sensors]]
- Processes the sensed data (**Computation**) [[IoT-Computation]]
- Communicates the data (**Communication**) [[IoT-Communication]]

![[image_IoT device-Power Consumption.png]]

> [!NOTE] **Some remarks** regarding [[IoT device-Power Consumption]]
> - **[[IoT-Communication]] is power hungry**
> 	- The difference between transmission and reception is small
> - [[IoT-Computation]] and [[IoT-Sensors]] also demand certain power
> 
> **HOW to deal with this? how to reduce energy consumption?**
## The basic strategy to reduce energy consumption
> [!NOTE] **make IoT devices sleep!**
- A device wakes-up when required (periodically, triggered by some external event)
- Then performs sensing, computation and communication
- Goes back to sleep
# [[IoT device-duty-cycle]]
## Duty cycle (activity factor) has to be very low in energy-constrained devices if long lifetime is required

