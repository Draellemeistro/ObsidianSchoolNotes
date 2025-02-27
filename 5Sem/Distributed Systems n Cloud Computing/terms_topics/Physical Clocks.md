for use in [[Clock Synchronization]]
- Some systems really need quite accurate absolute times
- UTC is the base of any international time measure
- International time based on atomic clocks still have a drift rate.
### UTC: Universal Coordinated Time
- based on the number of transitions per second of the cesium 133 atom (pretty accurate)
- At present, the real time is taken as the average of some 50 cesium-clocks around the world
- introduces a leap second from time to time to compensate that days are getting longer
#### UTC is broadcast through short wave radio and satellite. Satellites can give an accuracy of about $\pm 0.5 \text{ms}$ 

## Local System (computer) physical clocks 
- A counter register and a holding register in C-MOS RAM 
- The counter is decremented by a quarts crystals oscillator 
- When it reaches zero, an interrupted is generated and the counter is reloaded from the holding register
