# The basic types of RFID systems can be classified into:
1. **Inductive vs. Radiative systems** (<span style="color:rgb(255, 0, 0)">based on communication principle</span>).
	1. [[RFID-Inductive Systems]]
	2. [[RFID-Radiative Systems]]
2. **LF, HF, UHF systems** (<span style="color:rgb(255, 0, 0)">based on frequency bands</span>).
	1. [[LF RFID]]
	2. [[HF RFID]]
	3. [[UHF RFID]]
3. **Passive, Semi-Passive, and Active tags** (<span style="color:rgb(255, 0, 0)">based on the power source of the tags</span>).
	1. [[Passive RFID tags]]
	2. [[Semipassive RFID tags]]
	3. [[Active RFID tags]]

**This structure ensures you can explain the types effectively, linking the physical principles, frequency ranges, and tag power sources to their respective applications**

### **Based on Communication**

#### **Inductive RFID Systems**

- Operate in **near-field regions** where the wavelength is much larger than the antenna size.
- Energy from the reader decreases rapidly with distance (as the cube of the distance or faster).
- Typically used for **short-range applications** (e.g., LF RFID, HF RFID).
- Forward and backscattered waves are **not distinguishable**.

#### **Radiative RFID Systems**

- Operate in **far-field regions** where the wavelength and antenna sizes are comparable.
- Energy decreases with distance more gradually (as the square of the distance).
- Enable **longer-range communication** (e.g., UHF RFID).
- Forward and backscattered waves are **distinguishable**.

---

### **Based on Frequency Bands**

- **Low-Frequency (LF) RFID** (125–134 kHz):
    - Short-range communication, immune to water interference.
    - Applications: Animal identification, access control.
- **High-Frequency (HF) RFID** (13.56 MHz):
    - Medium-range communication with higher data rates.
    - Applications: Smart cards, asset tracking.
- **Ultra-High-Frequency (UHF) RFID** (300 MHz–3 GHz):
    - Long-range communication, supports multiple tag interrogation.
    - Applications: Toll systems, supply chain management, IoT.

---

### **Based on Tags**

#### **Passive RFID Tags**

- No onboard power source.
- Powered by energy from the RFID reader.
- Simple, low-cost, and commonly used.

#### **Semi-Passive (Battery-Assisted) RFID Tags**

- Contains a small battery to power its IC.
- Still relies on the reader to power its transmitter.

#### **Active RFID Tags**

- Contains a battery to power both its IC and transmitter.
- Used for longer ranges and advanced features.