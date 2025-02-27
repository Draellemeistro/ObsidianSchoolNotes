# Lektier til fredag 27 09
Til næste gang tjek op på:
- Læs USB-based Attacks
- Sæt sig ind i malware detection
	- Malware sets
	- Staitc detection
	- Sandboxing
- Former for maching learning

**Næste møde fredag klokken 12:00**

## What we got?
- 2015 microsoft, 0.5 terabyte, 20K malware samples dataset
	- has become standard benchmark for research on modeling malware behaviour
	- more? lots of research papers on it, i guess...
- MOTIF
	- contains **3,095 malware samples** from **454 families**, making it the largest and most diverse public malware dataset with ground truth family labels to date, *nearly larger than any prior expert-labeled corpus and **larger than the prior Windows malware corpus.***
	- Classifcation of Malware families (warning about noise created from bad labeling approaches)
	- Malware Open-source Threat Intelligence Family
- [Den her](https://ieeexplore.ieee.org/abstract/document/8328749): "*We convert **malware binaries to grayscale images** and subsequently train a CNN for classification*"
	- **Achieves 98.52% and 99.97% accuracy** on the Malimg and Microsoft datasets respectively.
- **Identifying Useful Features for Malware detection**
	- he task of distinguishing between malware and benign programs by learning their surface features, such as general file information and imported functions. **To make such attempts practical, a good balance among accuracy, learning time, and feature-data sizes is required**
	- we present a case study of feature selection in malware detection based on supervised machine learning. We used the Ember dataset as the target data and identified useful combinations of features in terms of accuracy, learning time, and data size.
- **Challenges in Evaluating Malware Clustering**
	- we believe, a cautionary note regarding the _significance_ of highly accurate clustering results, as can be impacted by testing on a dataset with a biased cluster-size distribution.


## USB-based attacks 2017

> [!NOTE] [Summary / Abstract](https://www.sciencedirect.com/science/article/abs/pii/S0167404817301578)
> In recent years, **USB peripherals have become an attractive tool for launching cyber-attacks**. In this survey, we review **29 different USB-based attacks** and utilize our new taxonomy to classify them into **four major categories**
> 
>They **utilize widely used USB peripherals**, such as keyboards, mice, flash drives, smartphones etc. 
>
>We address the **objective it achieves** and identify the a**ssociated and vulnerable USB peripherals and hardware.** 
>
>**Things:**
>- Data exfiltration
>- Stealing Network traffic
>- keystroke/mouse click injection
>- driver related attacks **==family==**
>  
![[Pasted image 20240927104036.png]]

![[Pasted image 20240927104059.png]]
### The USB protocol

- The PC host has an embedded hub, also called the root hub, which typically contains two or more USB ports.
- USB devices can be categorized into:
	-  **_I/O devices_** that add capabilities to the host and 
	- **_hub devices_** that only connect additional devices to the host.
- The USB cable usually has two purposes
	- It allows communication between a USB device and a host
	- It supplies electrical power to the USB device, if it is a *bus-powered* device.
- **==The USB cable connectors were specifically designed with the power pins longer than the signal pins, so that power would always be applied before signals.==**
- An endpoint forms a logical communication channel called a **_pipe_**. There are two types of pipes:
	- **_Message pipe_:** used for _control transfers_ in which short, simple commands are sent to the device and status responses are sent from the device.
	- **_Stream pipe_:** used for any of the following data transfer types:
		- *Isochronous transfers* for functions that require timing coordination at some guaranteed data rate but with possible data loss, e.g., real-time audio or video.
		- _Interrupt transfers_ for functions that need guaranteed quick responses with bounded latency, e.g., mice and keyboards.
		- _Bulk transfers_ for large sporadic transfers using all remaining available bandwidth, but with no guarantees on bandwidth or latency, e.g., file transfers.

- Connecting a USB device to the host initiates a process called e_numeration_. In general, enumeration involves four steps:
	- **Detecting that a device has been connected**: When a USB device is plugged into a USB host there is a change on the data lines by which the host detects a device has been connected.
	- **Determining device speed**: The change on the data lines is also used to identify the speed of a device.
	- Determining [device descriptors](https://www-sciencedirect-com.zorac.aub.aau.dk/topics/computer-science/device-descriptor "Learn more about device descriptors from ScienceDirect's AI-generated Topic Pages"): Devices are identified by descriptors that they send to the host. This step basically follows a question and answer process:
		- the host will send a _Get_Device_Descriptor_ command, and the device will send its descriptor length followed by the actual descriptor.
		- he device is reset again and given a unique logical address via a _Set_Address_ command.
		- host will send a _Get_Configuration_Descriptor_ command in order to establish the device's configuration. The device will reply by sending its configuration descriptor which includes a hierarchy of interface, endpoint, and (optionally) class specific descriptors.
### USB attacks
#### Programmable microcontrollers
1. Rubber Ducky ([RIFT recon](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0415)) is a commercial keystroke injection attack platform released in 2010.
2.  PHUKD/URFUKED: The **P**rogrammable **H**ID **U**SB **K**eyboard/Mouse **D**ongle ([Crenshaw, 2010](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0105)) (PHUKD) and the **U**niversal **RF U**SB **K**eyboard **E**mulation **D**evice (URFUKED)
3. USBdriveby ([Kamkar](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0225)) is another Teensy based USB hardware Trojan developed by white hat security researcher, Sam Kamakar
4. Evilduino is a USB hardware Trojan developed by Rashid Feroz and based on an Arduino microcontroller ([Feroz](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0140)) (in contrast to the previously mentioned **PHUKD/URFUKED** attacks which are based on the Teensy microcontroller).
5. Unintended USB channel: [Clark et al. (2010)](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0090) developed a proof of concept (POC) USB hardware Trojan that [exfiltrates data](https://www-sciencedirect-com.zorac.aub.aau.dk/topics/computer-science/exfiltrate-data "Learn more about exfiltrates data from ScienceDirect's AI-generated Topic Pages"), based on unintended USB channels.
6. TURNIPSCHOOL ([NSA Playset](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0355)) is a hardware implant concealed within a USB cable developed by [wireless security](https://www-sciencedirect-com.zorac.aub.aau.dk/topics/computer-science/wireless-security "Learn more about wireless security from ScienceDirect's AI-generated Topic Pages") researchers, Michael Ossman, Dominic Spill, and Karoline Busse, as part of the NSA Playset program, an initiative that aims to duplicate, in open-source, the technologies exposed in the NSA surveillance catalog
7. R IT attack via USB mass storage:  [ Mulliner and Michéle (2016)](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S0167404817301578#bib0315) described a novel TOCTTOU attack based on changing the content of files while the mass storage device is connected to the attack target. The attack succeeds if the check code verifies the signature of the original benign file and the install operation uses the maliciously modified file.
# andet

Good 
[Microsoft Malware Classification challenge](https://arxiv.org/abs/1802.10135?fbclid=IwZXh0bgNhZW0CMTAAAR1g7PJEcU8o8TuvDysHQLBodTY8DWYQDn3q1b1NTH-N13JvpTbZWtUHmCU_aem_S6J2-8zzOjpSNCqG5NTaFA)



[Microsoft Malware Classification Challenge](https://www.kaggle.com/c/malware-classification?fbclid=IwZXh0bgNhZW0CMTAAAR0q_FprS1KHfGiL3geg3YZwKhjLiq3NExOpBYzO_jyqURb0Z0Pxy2n2Dp0_aem_9NLJ6MJzIcv8EAb1y1qO1A) 

[https://www.sciencedirect.com/science/article/abs/pii/S0167404822003133](https://www.sciencedirect.com/science/article/abs/pii/S0167404822003133?fbclid=IwZXh0bgNhZW0CMTAAAR3pKk8Js-lPaLu__nSTjqJtuTSVwv_lzH2YHPtdYCwE0xmKWo9nAZtAIf4_aem_0LJd--FDgvzTDmzRmyT4fg) # 

[malware-family](https://www.sciencedirect.com/topics/computer-science/malware-family?fbclid=IwZXh0bgNhZW0CMTAAAR0m7h5wfehApRuB3NyihnncXI67-fxdxRKQdN3wp685vIfVF_HF2vRFnwY_aem_FL9ZaPYVnW_JPZCS3wOX_w) 

[[Malware Classification with Deep Convolutional Neural Networks](https://ieeexplore.ieee.org/abstract/document/8328749)](https://ieeexplore.ieee.org/abstract/document/8328749?fbclid=IwZXh0bgNhZW0CMTAAAR1g7PJEcU8o8TuvDysHQLBodTY8DWYQDn3q1b1NTH-N13JvpTbZWtUHmCU_aem_S6J2-8zzOjpSNCqG5NTaFA) 

[Identifying Useful Features for Malware Detection in the Ember Dataset](https://ieeexplore.ieee.org/abstract/document/8951564?fbclid=IwZXh0bgNhZW0CMTAAAR02x_ya-ZJdN50XoaaW98kTQYmNz9bOZcqfpn9q_P7MY3j6Nk6dziIeML4_aem_JlccILeA1sWnIm6Ff3xkfg) 

[On Challenges in Evaluating Malware Clustering](https://link.springer.com/chapter/10.1007/978-3-642-15512-3_13?fbclid=IwZXh0bgNhZW0CMTAAAR0m7h5wfehApRuB3NyihnncXI67-fxdxRKQdN3wp685vIfVF_HF2vRFnwY_aem_FL9ZaPYVnW_JPZCS3wOX_w) 

# [[State MachineLearning]]

Måske
# Ikke kigget på
- https://virusshare.com/about
	- Repository af Malware samples '_to provide security researchers, incident responders, forensic analysts, and the morbidly curious access to samples of live malicious code._'
##  Malware collection and analysis
[https://ieeexplore.ieee.org/abstract/document/8102915](https://l.facebook.com/l.php?u=https%3A%2F%2Fieeexplore.ieee.org%2Fabstract%2Fdocument%2F8102915%3Ffbclid%3DIwZXh0bgNhZW0CMTAAAR2rWGmkp_lLlsXIpTIPRpPLNTzTHezZc6XUBdNO9QsYJJg5807ezVU9STA_aem_pTJvlfdulFTJIpxz5QH4rA&h=AT0-_n6barqcApKer3K-BwmeMEe6Nm1WSUIRQVYPSXEoWoZGF7czRwwUAo4SRqH3IMIm4wfRflUIv4QnM7ZY4ls-F0RlqvSOtReadqVwgWEjd9be5Atikt3WQx_uoZPSAtk) 

## Endgame Malware BEnchmark for Research (EMBER)

## ss
[https://arxiv.org/abs/2103.00602](https://l.facebook.com/l.php?u=https%3A%2F%2Farxiv.org%2Fabs%2F2103.00602%3Ffbclid%3DIwZXh0bgNhZW0CMTAAAR3T8En_jQXo9rnuNmopl0r0eXY8xTWzZlHeooLg_eYr3kt1LLXpEAlXP1E_aem_a0ZUwtaIBMPy3B1npLYskQ&h=AT0-_n6barqcApKer3K-BwmeMEe6Nm1WSUIRQVYPSXEoWoZGF7czRwwUAo4SRqH3IMIm4wfRflUIv4QnM7ZY4ls-F0RlqvSOtReadqVwgWEjd9be5Atikt3WQx_uoZPSAtk) 

## ss
[https://ieeexplore.ieee.org/abstract/document/9474321](https://ieeexplore.ieee.org/abstract/document/9474321?fbclid=IwZXh0bgNhZW0CMTAAAR0dbXH2RWjO5cUw7Txty_uhDTww36ahm3CvJBmuwGYLaNIK_JxImZ9sdzc_aem_gvcpvbREDvbOowdH2LcBxg) 

## ss
[https://ieeexplore.ieee.org/abstract/document/8568018](https://l.facebook.com/l.php?u=https%3A%2F%2Fieeexplore.ieee.org%2Fabstract%2Fdocument%2F8568018%3Ffbclid%3DIwZXh0bgNhZW0CMTAAAR1g7PJEcU8o8TuvDysHQLBodTY8DWYQDn3q1b1NTH-N13JvpTbZWtUHmCU_aem_S6J2-8zzOjpSNCqG5NTaFA&h=AT0-_n6barqcApKer3K-BwmeMEe6Nm1WSUIRQVYPSXEoWoZGF7czRwwUAo4SRqH3IMIm4wfRflUIv4QnM7ZY4ls-F0RlqvSOtReadqVwgWEjd9be5Atikt3WQx_uoZPSAtk)

## sss
[OOO](https://arxiv.org/abs/1802.10135?fbclid=IwZXh0bgNhZW0CMTAAAR0dbXH2RWjO5cUw7Txty_uhDTww36ahm3CvJBmuwGYLaNIK_JxImZ9sdzc_aem_gvcpvbREDvbOowdH2LcBxg)
