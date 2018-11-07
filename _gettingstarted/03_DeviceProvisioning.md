---
title: Device Connection
description: How to provide the IoT Central connection information to the device
position: 3
---

> **IMPORTANT**:
>
> For the first installation of a new X400 device (even for cellular versions) you need an Internet connection via ethernet (with a DHCP enabled router).
{: .warning}

At startup X400 does not have any connection information. Any info about IoT Central connection should be provided via special Arduino library functions, using a specific code on app-processor.
Once the info are received, **X400** connects automatically to the cloud, waiting to be paired with a specific account.


**How to get the Device Connection Info?**
The device connection info are available on the device explorer section of IoT Central. Simply select the desired device template and open the desired device (if no real device are available, please create a new one).
To access all the info needed by device, you have to click on the **Connect** button on the device page.
The info needed by the device are:
- **Scope ID**
- **Device ID**
- **Primary Key** of *Shared Access Signature (SAS)* section

> Take note of those parameters since them should be added on the app-processor Arduino firmware.
{: .info}


