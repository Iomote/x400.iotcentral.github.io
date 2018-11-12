---
title: Initialization
position: 2
---


### Iomote object initialization
Most of the following commands leverages on the object Iomote, that is instantiated during the initialization phase. In the setup function it must be initialized using the proper command:
~~~ cpp
void Iomote.begin(const char *appname, uint8_t vers0, uint8_t vers1, uint8_t vers2)
~~~
**Parameters**
- **appname**: the buffer containing the name of the app (max length 100 chars).
- **vers0, vers1, vers2**: main, middle and lower version number for the app. (values: 0-255 for each number)

**Returns**
- None

The method initializes the hardware and communicates the Application name and version to the **Iomote Core** processor. Those parameters are sent to the Cloud only when changed, keep in mind each device has a max number of messages available per day.

> **WARNING**: the **Iomote.begin** method is mandatory for the app to work properly. **NEVER remove it from your code!**
{: .error}

The **App name and App version** running on a specific device are shown on *Device Template Properties section*.


---


### Setup IoT Central Device Connection parameters
~~~ cpp
int8_t Iomote.iotCentralInfo(char* ScopeId, char* DeviceId, char* PrimaryKey)
~~~
**Parameters**
- **ScopeId**: the char array containing the Scope Id string.
- **DeviceId**: the char array containing the Device Id string.
- **PrimaryKey**: the char array containing the Primary Key string.

**Returns**
- 0 in case of success
- error code (refer to error codes table)
 
Using this method the user configures the device with all the parameters needed by the IoT Central connection. Once set, such parameters are stored on device internal memory. It is enought to set IoT Central Connection parameters once on each **X400** device.


---


### Syncing the real time clock
~~~ cpp
time_t Iomote.rtcSync()
~~~
**Parameters**
- None

**Returns**
- a time_t variable containing the updated date/time. 
 
The internal RTC of the application processor is update at the device startup, but sometimes it may happens (especially with no internet connection) that the date/time is not updated so, at runtime, it's possible to force an update with this command. 

