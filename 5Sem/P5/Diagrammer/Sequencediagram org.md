
### USB enumeration procedure
```UML
title USB enumeration procedure

Host->Device:GetDeviceDescriptor
Host<--Device:drag to move
Host->Device:ResetDevice/AssignAddress
Host<--Device:response
Host->Device:GetConfigDescriptors
Host<--Device:response
Host->Device:GetInterfaceDescriptors
Host<--Device:response
Host->Device: Load Drivers
Host<--Device:USB Communications
```
