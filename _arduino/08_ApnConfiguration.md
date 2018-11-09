---
title: APN Configuration
description: hot to customize APN parameters for mobile network connection
position: 8
---

To configure APN parameters on **Iomote Core** non-volatile memory the user have to set them via **Application processor's code**. Since such parameters are stored on non-volatile memory, it is enought to insert the setup command atleast once on **App processor's code** on device lifetime. If user should change APN configuration, he can always change them using a new arduino firmware.

---

### **Setup APN Parameters**
~~~ cpp
void Iomote.apnSetParams(int mode, char* server, char* username, char* password, char* ip, char* dns1, char* dns2)
~~~ 
**Parameters**
- **mode**: the auth mode to use
 - **0** NO Auth is used
 - **1** PAP Auth is used
 - **1** CHAP Auth is used
- **server**: server name
- **username**: user name. If no username should be used, please use NULL
- **password**: password. If no password should be used, please use NULL
- **ip**: ip address to be used. If no ip address should be specified or a dynamic ip should be used, please use NULL
- **dns1**: dns1 ip address to be used. If no ip address should be specified or a dynamic ip should be used, please use NULL
- **dns2**: dns2 ip address to be used. If no ip address should be specified or a dynamic ip should be used, please use NULL

