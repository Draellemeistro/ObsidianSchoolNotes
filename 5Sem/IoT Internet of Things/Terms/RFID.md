> [!danger] Radio Frequency Identification

Wireless technology used for exchange of **short messages** between the reader and the [[RFID-tags|tags]]
- [[RFID-tags|tags]] are very simple and cheap devices, whose main purpose is to identify the object to which they are attached to
	- <span style="color:rgb(255, 0, 0)">the main idea</span> was to replace the bar-code with a faster (more automatized), non-line of sight system
- The cost of the [[RFID-tags|tag]] should be significantly lower than the cost of object it identifies
	- either very cheap [[RFID-tags|tag]] or a very expensive object
- ![[image_RFID.png]]
> [!NOTE] [[RFID]]: Examples of use (**identification**)
> Car keys -- Student IDs -- Social security numbers -- License plates

> [!tip] [[RFID]]: Examples of **applications**
>- Livestock tagging
>- Wild animal tracking
>- Automatic toll collection
>- airline baggage tracking
>- inventory tracking
>- building access control
>- tracking of goods
>- anti-theft systems

## [[RFID-Components|Components]] of RFID system
- [[RFID-Reader|reader]] (aka interrogator)
- [[RFID-tags|tag]] (aka transponder)
- Link between the two:
	- Downlink (aka forward link)
	- Uplink (aka backward/reverse link)
- Reader is a (_more_) powerful device
	- The reader antenna may be physically separated from it
- [[RFID-tags|tag]] is simple device that has integrated antenna and an IC (chip) containing the operational logic

# Types of [[RFID]] systems [[RFID-system-types]]

> [!NOTE]
> ![[image_RFID-1.png]]

## [[RFID-Inductive Systems]]
- **Wavelength is much larger than the antenna**
- Almost all the energy from the reader antenna is contained in a small region around it
	- The energy of the forward wave decreases as the cube of the distance or faster
- <span style="color:rgb(255, 0, 0)">The reader and the tag are very close to each other</span>
	- There can not be distinguished separate forward and backscattered waves
## [[RFID-Radiative Systems]]
- **Wavelength and antenna sizes are comparable**
- Larger distances can be covered
	- The energy of the wave decreases as the square of the distance
- Forwad and backscatter waves can be distinguieshed
## [[LF RFID]]
- Very low data rates
- Animal and human ID:
	- The system is immune to the presence of water (i.e. impact of tissues)
	- [[RFID-tags|tags]] are relatively costly and require a procedure for installation (which also costs)
- Access Control:
	- easy to implement a tag in a card or key badge
- <span style="color:rgb(255, 0, 0)">Interrogation is one-by-one</span> (**_SLOW_**), but humans and animals tend not to move very fast
## [[HF RFID]]
- higher data rates
- non-contact smart cards
	- Short range is favorable for security reasons or inadvertent activations
- asset tracking:
	- Short range requires use of large antennas, large form-factors, making sure that the items pass by closer to the reader
- <span style="color:rgb(255, 0, 0)">Interrogation is one-by-one</span>
## [[UHF RFID]]
- high data rates
- long ranges
- automatic tolling
- supply chain management, inventory tracking...
- Multile tags can be interrogated at the same time (**requires use of [[multiple-access protocols]]!!**)
- <span style="font-weight:bold; color:rgb(255, 0, 0)">The likely candidate for widespread IoT use</span> 

# Types of [[RFID-tags]]
Tags can be **passive, semipassive**(aka battery-assisted)**, Active**
### [[Passive RFID tags]]
- No power source of their own
- The reads powers through its transmission both the IC and the tag transmitter
### [[Semipassive RFID tags]] (_aka battery-assisted_)
- A (small, coin sized) battery is used to power the IC of the tag
- The tag transmitter is powered by the transmission of the reader
### [[Active RFID tags]]
- Battery powers both the IC and the conventional transmitter
![[image_RFID-tags-1.png]]


# [[RFID Protocols]]
- A mix of proprietary and standardized solutions
	- Use of protocol depends on the application, [[Frequency bands]], tag type etc......
## Some [[RFID]] protocols
![[image_RFID-2.png]]
### [[Gen2 protocol]]
> [!NOTE] ISO 1800-6c, EPC global Class 1 Generation 2
- [[Electronic Product Code (EPC)]]
	- A universal identifier that provides a unique identity for every **physical object** anywhere in the world
	- does not necessarily have to involve [[RFID]]
- The protocol is based on **dynamic frame [[Slotted ALOHA]]**
- also known as **Q protocol**
- Gen2 operates in inventory rounds, initiated by the reader
- <span style="font-weight:bold; color:rgb(255, 0, 0)">PLUS MORE (see [[Gen2 protocol]])</span> 