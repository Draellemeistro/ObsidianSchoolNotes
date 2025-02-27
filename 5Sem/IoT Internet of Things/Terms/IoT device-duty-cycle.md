> [!danger] <span style="font-weight:bold; color:rgb(21, 32, 9)">(i.e., sleeping periods)</span>

## Duty cycle (activity factor) has to be very low in energy-constrained devices if long lifetime is required
#### Back of the envelope calculation
- We neglect power consumption of [[IoT-Sensors]] and [[IoT-Computation]]
##### Typical round (cycle):
![[image_IoT device-duty-cycle.png]]

> [!NOTE] **Energy spent per round:**
> $$E_{R}=P_{RX}T_{RX}+P_{S}T_{S}+P_{TX}T_{TX}+P_{\text{sleep}}T_{\text{sleep}}$$

| Activity                   | Power consumption | Consumption normalized by $P_{TX}$ |
| -------------------------- | ----------------- | ---------------------------------- |
| Transmission - $P_{TX}$    | $\sim$ 100 mW     | 1                                  |
| Reception - $P_{RX}$       | $\sim$ 50 mW      | 0.1-1                              |
| Channel sensing - $P_{S}$  | $\sim$ 50 mW      | 0.1-1                              |
| Sleep - $P_{\text{sleep}}$ | < 1 mW            | 0-0.001                            |
$$E_{R}=P_{RX}T_{RX}+P_{S}T_{S}+P_{TX}T_{TX}+P_{\text{sleep}}T_{\text{sleep}}$$
$$\approx P_{RX}(T_{RX}+T_{S}+T_{TX})+P_{\text{sleep}}T_{\text{sleep}}$$
$$\approx P_{RX}(T_{RX}+T_{S}+T_{TX})$$
$$\approx P_{on}T_{on}$$

## [[IoT device-duty-cycle|Duty cycle]]:
$$DC=\frac{T_{on}}{T_{R}}=\frac{T_{on}N_{R}}{T_{R}N_{R}}=\frac{t_{on}}{t}$$
## Battery energy resource:
$$E=P_{on}T_{on}N_{R}=P_{on}T_{on}$$

> [!NOTE] Typical Values
> - $E=5000\text{ J}=5000\text{ Ws}$
> - $P_{on}=50\text{ mW}$
> - $t_{on}=\frac{E}{P_{on}}=10^5 \text{ s  }\approx$ **1 DAY!!!!!** 

**THUS:** $$DC \approx \frac{1\text{ day}}{t[\text{ day}]}$$
#### Example
- For a target life-time of 10 years, the [[IoT device-duty-cycle|Duty cycle]] is: $DC \approx \frac{1}{3650}\approx 0.03\%$
- This means that the device is active for 24 seconds daily

## Low duty cycle ensures long life but creates problems:
- Latency in data delivery
- Latency in control and management of the network

[[Duty cycle and Battery energy]]