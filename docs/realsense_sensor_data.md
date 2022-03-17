---
layout: default
title: Sensor Data
parent: SmartClean Sensors
grand_parent: RealSense
has_children: true
has_toc: true
nav_order: 2
---

# Sensor Data
This page describes the format of raw data provided by our Sensors and Devices.

Note:
Raw data from sensors is accessible when third party push is enabled 
in RealSense for a property or through a dedicated provisioned data lake.


## General Data Format
The general format of data by all our devices and sensors is:
```json
{
  "t": <string>,  // Timestamp in the local timezone region of the device (string format: yyyymmddhhmmss)
  "v": <custom type>  // Realtime Data from Sensor depending on the type of the Sensor
  "unixT": <number>  // Unix time in milliseconds
  "DEVID": <string>,  // Slot ID for the Device
  "Region": <string>,  // Timezone string in JODA format (See reference at bottom of page)
  "time": <string>,  // Timestamp in string format: YYYY-MM-DDTHH:mm:ss+offset
  "DevType": <string>,  // Type of the Device Slot (Example: PC for People Counter, FD for feedback etc).
  "PID": <string>,  // ID of the Project.
  "InsID": <string>,  // ID of the Location / Zone where the Device Slot is located.
  "Display": <string>,  // Name of the Device Slot (for identification)
  "dow": <string>,  // Day of Week - 0: Sun to 6: Sat
  "month": <string>,  // Month of the year (1 - 12)
  "hour": <string>,  // Hour of day (0 - 23)
  "dom": <string>  // Day of month (0 - 31)
  "minute": <string>  // Minute of the Hour (0 - 59)
}
```
Notes:
1. For value of *t*, the timestamp string format represents the following:
yyyy is year, mm is month, dd is day, hh is hour, mm is minutes
2. To get the region timezone for the device see the attribute *Region*


## Custom Data Format
The value of attribute: *"v"* in the general data format is based on the device slot type

Device slot type is described in the [parent page](/realsense_sensors.html)

To see the custom data format for each device slot type, visit the page corresponding to the desired category below.

Custom data format for device types:
1. [Usage monitoring](/realsense_sensor_data_pc.html)
2. [Feedback reporting](/realsense_sensor_data_fd.html)
3. [Spill detection](/realsense_sensor_data_wd.html)
4. [Consumable monitoring](/realsense_sensor_data_cmd.html)
5. [Bin fill level sensing](/realsense_sensor_data_bin.html)
6. [Air quality monitoring](/realsense_sensor_data_aq.html)

