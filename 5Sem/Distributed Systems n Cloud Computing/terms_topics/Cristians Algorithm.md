for [[Clock Synchronization]]
- Client $A$ contacts server $B$
- $B$ sends its current timestamp with $\text{T\_server}$ stamp
- $A$ estimates the RTT (round trip time) and adjusts its clock
- It only achieves synchronization if the round trip time (RTT) of the request is short compared to required accuracy.
- **To improve accuracy:** Multiple measurements to take the average.
![[image_Cristians Algorithm.png]]
