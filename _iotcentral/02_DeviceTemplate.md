---
title: Device Template
position: 2
---

To define the device type, behaviour and properties, IoT Central uses the *device templates*. All the **X400** devices have some common template properties, but the user can customize any other aspect of the template based on the specific application needs.

The **Device Template** has the following properties:
* **Measurements**: the telemetries, states and events the device sends to the application.
* **Settings**: the configurations that an operator can set on the device.
* **Properties**: metadata that an operator can define, or the device can update.
* **Commands**: definition of tasks to be triggered on the device.
* **Rules**: automate behavior in the application based on data sent from a device.
* **Dashboards**: customizable views of a device in the application.

---

### **Measurements**
**Measurements** are all the telemetry data sent by the user application to the IoT Central cloud service.
Measurements are totally configurable by the user, and are dependant from app-processor running code. Later in the documentation there will be shown some examples.

---

### **Settings**
**Settings** are special properties the user want to be in sync with the device. Each time User modify a setting the device is notified. If device is currently offline, all last modified settings will be sent to device.
**X400** device do not use any special settings configuration. User can have access to all the settings using Arduino app-processor code. Later in the documentation there will be shown some examples.

---

### **Properties**
There are 2 kind of **properties** on IoT Central: *Device properties* and *Application properties*.
**Application properties** are NOT sent to device, and devices cannot access to such data.
**Device properties** are reported by device each time is needed, or by app-processor specific request. Later in the documentation there will be shown some examples.

---

### **Commands**
**Commands** are some special messages sent to devices. Them permits the execution of certain tasks on the devices (for example start a firmware update, or redirect such tasks to app-processor application).

---

### **Rules**
**Rules** are some automated behaviour user can customize based on its needs. **X400** devices are not aware of rules and absolutely do not depends (or have access to) them.

---

### **Dashboard**
**Dashboard** can be configured with all the previously defined template aspects. User can customize it to have a fast access of all the devices and application informations in a single screen.

---
