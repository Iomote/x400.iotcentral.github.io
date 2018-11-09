---
title: x400 template
description: how to create a x400 compatible device template
position: 2
---

Every IoT Central device type should have template. Such template defines lots of devices properties and behaviours.
> The creation of a **X400 compatible** device template is not necessary, but we suggest to follow the steps described to get all the **Iomote** special features embedded on **X400 devices**.
{: .info}

### **Template creation**

To get the best from a **X400** compatible device template some properties can be added. Such properties are automatically sent by the device, and user application MUST NOT use the provided **Field Names** on it's own **App-processor's code**.

---

#### **Properties** 

Following is a list of device properties sent by **Iomote Core** processor, usefull to keep track of some device aspects. You can create them using the *Edit Template* button on the **Properties** tab of template view
- **Firmware Version**
    -   **Display Name**: Firmware Version
    -   **Field Name**: firmware
    -   **Data Type**: text
- **Network interface**
    -   **Display Name**: Network Interface
    -   **Field Name**: interface
    -   **Data Type**: text
- **Sim Iccid**
    -   **Display Name**: Sim Iccid
    -   **Field Name**: iccid
    -   **Data Type**: text
- **App Name**
    -   **Display Name**: App Name
    -   **Field Name**: appName
    -   **Data Type**: text
- **App Version**
    -   **Display Name**: App Version
    -   **Field Name**: appVersion
    -   **Data Type**: text

---

#### **Commands** 

Here are the available commands the user can configure to perform some already defined tasks on **Iomote Core OS**. Such commands are defined on the device OS and the user applicaton MUST NOT rely on the same names for **App-processor's code**.

- **Commands** following is a list of device commands present on **Iomote Core** processor OS, usefull to perform some mantainance tasks. You can setup them using the *Edit Template* button on the **Commands** tab of template view
    - **OS Update** TODO: add the OS Update command description
    - **App Update** TODO: add the App Update command description
    - **User Messages** TODO: add the User message method description (all the other names are available, right?)
