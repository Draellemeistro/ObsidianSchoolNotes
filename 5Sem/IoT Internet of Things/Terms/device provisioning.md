
> [!NOTE] **TLDR:** [[device provisioning]]
> **preparing and configuring IoT devices so they can securely connect** to a network or cloud service, **communicate** with other devices, and **perform** their intended **functions**.
> <span style="color:rgb(255, 0, 0)">ensures that devices are correctly registered, authenticated, and configured for secure operation.</span>

![[image_device provisioning.png]]

- **bootstrapping with basic device information.**
	- At a minimum, a device needs an ID and basic metadata
- **Credentials and authentication required for secure communications**
	- For example, the device can be provided a token or key that can be used for ongoing communications.
	- Such credentials might have an expiration time.
- **Authorizing the device**
	- Authorization establishes the permissions of the device to interact with the application or other services, relying on the authentication credentials above
	- Authorization in the specific permission of the device ID and credential with a specific resource it can use
- **Setting up the network connection**
	- A device needs a network connection to be able to communicate with other services and to transmit data.
- **Registering the device**
	- Applications need to know which devices are available
	- A device registry keeps track of which devices are in use, manages the cloud side of authentication, and associates devices with specific data and resources (such as telemetry topics and state storage).