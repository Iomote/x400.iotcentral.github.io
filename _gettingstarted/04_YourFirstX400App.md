---
title: Your first X400 app
description: sending data to the cloud
position: 4
---

Let’s code your first Arduino App to send data from the device to the cloud. First connect your X400 to your computer via USB, then open the Arduino IDE and set the right virtual COM port (**menu Tools -> Port**). Create a new Sketch a copy/paste the code:
- go to the GitHub page for the [**getting started app**](https://github.com/Iomote/iomote-app-iotcentral-getting-started) and copy and paste the [**code**](https://raw.githubusercontent.com/Iomote/iomote-app-iotcentral-getting-started/master/x400IotcentralGettingStarted/x400IotcentralGettingStarted.ino) file content on a new Arduino x400 app
- replace the strings for device connection with the values rovided by your **IoT Central** application dashboard:
    - **SCOPE_ID**
    - **DEVICE_ID**
    - **PRIMARY_KEY**
  
Then, in the menu, select **Sketch -> Verify/Compile**.
Now your App is compiled and ready to be uploaded to your X400 device: **Sketch -> Upload** and wait for the device to be ready.

> **App usage**
>
> open the serial monitor inside the Arduino IDE (**Tools -> Serial monitor**) and select the proper COM port, so you’ll get debug messages.
> 
> Push the front button to send messages to the cloud. 
{: .success}
