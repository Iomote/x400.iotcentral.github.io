---
title: Before starting
position: 1
---

Before starting you have to execute some steps to get your system ready to work with X400 devices.
- Get an [**account on Azure IoT Central**](https://apps.azureiotcentral.com/). 
- Once an account is created (or if already have your own account), login to IoT Central and create a new application (or use a previously created application). If you are creating a new application, please avoid the samples and create a custom blank application from scratch.
- Install the **Arduino IDE** on your computer (you can download it form [arduino website](https://www.arduino.cc), available for Windows - Linux - Mac).


> **WARNING**: (for Windows users) download the installer from arduino website, not the app from the Windows store (we had some problems with that version of the IDE).
{: .error}

- Once the Arduino IDE is installed you have to add the **X400 libraries**:
    1. Go to menu **File -> Preferences**
    2. On the **Additional board manager URLs**, add: **https://github.com/iomote/arduino-ide-bsp/raw/master/package_iomote_index.json**  (use comma if there are other addresses) and confirm.
    3. Open the **Board manager** (menu Tools -> Board:xxx -> Board Manager)
    4. Search and install the package **Arduino SAMD Boards** (32.bits ARM Cortex-M0+) by Arduino
    5. Search and install the package **Iomote X400** by Iomote
    6. Open the **Library Manager** (menu Sketch -> Include Library -> Manage libraries)
    7. Install the library **RTCZero** by Arduino
    8. **Select X400** from Tools -> Board:xxx -> Iomote X400
    9. Now the **IDE is ready** to create App for X400.
