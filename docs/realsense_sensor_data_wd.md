---
layout: default
title: Spill detection device data
parent: Sensor Data
grand_parent: SmartClean Sensors
nav_order: 5
---

## Data format for spill detection devices
Device slot type applicable:
- SMARTCLEAN#WD

Format of attribute: *"v"* in the general data format:
```json
{
  "value": <number>  // value of 1 represents spill detected.
  "AreaP": <number>  // value represents percentage of area that is wet  
}
```
Notes:
1. Where "value" indicates whether spill detected or not
2. The size of spill is given by the "AreaP" value 
   (Represents how much area (in percentage) of device field of view area is wet.)
3. For **more details about our spill detection device**
please visit our [help center page](https://helpcenter-smartclean.webflow.io/help-installation/wf-2101-01-how-it-works)

---

#### Example data:

```json
{
  "t": "20211210152132",
  "v": {
    "value": 1,
    "AreaP": 5.5  
  },
  "unixT": 1639120892,
  "DEVID": "DemoWD1",
  "Region": "Asia/Singapore",
  "time": "2021-12-10T15:21:32+0800",
  "DevType": "SMARTCLEAN#WD",
  "PID": "DemoProject",
  "InsID": "DemoLocation",
  "Display": "Demo Spill Detector 1",
  "dow": "5",
  "month": "12",
  "hour": "15",
  "dom": "10",
  "minute": "21"
}
```

#### Example use case:
Raise an incident if the following condition in data is met: 
Value of *"value"* is 1 and value of *"AreaP"* crosses a certain threshold.

This indicates that a spill of considerable size has been detected within the field of view of the device.

