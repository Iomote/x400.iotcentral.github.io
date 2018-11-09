---
title: Cloud communication
position: 6
---

X400 can be considered an "always on" device, permanently connected with the cloud. The **Iomote Core** manages the connection with the cloud and the messages. All the messages are sent from the application processor to the **Iomote Core**, that is responsible of storing it inside the non-volatile memory and delivering it to the cloud. If there is some issue with the connection is not a problem, because all the messages are stored inside the non volatile memory. So, as soon as the application processor sends them to the **Iomote Core**, they are permanently stored until they are correctly delivered to the cloud. No matter if the network goes down, no matter if the power cable is unplugged, messages are stored inside the flash memory, so, when an internet connection will be available (ethernet or 2G/3G), the device will send each pending message in memory.

In addition, X400 **Iomote Core** can receive user messages from cloud (cloud to device messages). Up to 10 messages can be stored on non-volatile memory, so **App processor** can read them without worry about _timings_. User messages are delivered using a special IoT Central **Command**.


---


### **Data Messages**
~~~ cpp
int8_t Iomote.sendMessage(char* payload)
~~~
**Parameters**
- **payload**: the message to be sent to cloud. *Payload max length is 3750 bytes*

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---


### **Properties**
~~~ cpp
int8_t Iomote.sendProperties(char* propertyPayload)
~~~
**Parameters**
- **propertyPayload**: the properties Json message to be sent to cloud. Payload max length is 1024 bytes. All the properties sent with this command can be configured on IoT Central Device Template. User should avoid to add the **Iomote Core OS** reserved template properties names for json object fields. Only 1-level nested Json properties are accepted.

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---



### **Pending messages counter**
To get the counter of the currently queued messages, but not sent yet to the cloud by the Iomote Core processor:
~~~ cpp
int8_t Iomote.messagesPending(int16_t* pend)
~~~
**Parameters**
- **pend**: the pointer to your int16_t variable to store data read from Iomote Core (ex: use iomoteClass.messagesPending(&myVariable); on your code)

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---

### **Check if Cloud to device User Messages or Settings are available**
~~~ cpp
bool Iomote.userMessageAvailable()
~~~
Checks if there are any user messages on **Iomote Core** waiting to be sent to **App processor**. 

**Returns**
- **true** in case of messages pending present on non-volatile memory
- **false** if no messages are present on non-volatile memory


---

### **Read User Messages content**
~~~ cpp
int8_t Iomote.userMessageRead(char* buffer)
~~~
Copies the oldest user message content to provided buffer. When **App processor** uses such command, the **Iomote Core** erase the message from non-volatile memory
**Parameters**
- **buffer**: the buffer to use to copy message content. buffer max length should be at least 4096 bytes (the limit of cloud to device user messages size).

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---

### **Clear all User Messages**
~~~ cpp
int8_t Iomote.userMessageClearAll()
~~~
Forces the erasing of all messages present on **Iomote Core** non-volatile memory, without reading them.

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---

### **Read Settings content**
~~~ cpp
int8_t Iomote.settingsRead(char* buffer)
~~~
Copies the latest received settings data to provided buffer. When **App processor** uses such command, the **Iomote Core** erase the message from memory
**Parameters**
- **buffer**: the buffer to use to copy message content. buffer max length should be at least 4096 bytes (the limit of cloud to device user messages size).

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---

### **Enable and Disable Cloud connection**
~~~ cpp
int8_t Iomote.cloudEnabled(bool* cloudIsEnabled)
~~~
Turns On or Off the cloud connection. In this way the User can force the device to be disconnected from network. When **App processor** uses such command, the **Iomote Core** changes (if needed) the cloud connectivity status.
**Parameters**
- **cloudIsEnabled**: if true the device is enabled to be connected to IoT Central, otherwise the device will not be connected and cloud data could not be exchanged.

**Returns**
- **0** in case of success
- **error code** otherwise (refer to [error codes table](/#arduino08_ErrorCodes))


---

