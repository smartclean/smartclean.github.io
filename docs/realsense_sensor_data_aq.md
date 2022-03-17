---
layout: default
title: Air quality device data
parent: Sensor Data
grand_parent: SmartClean Sensors
nav_order: 6
---

## Data format for air quality detection devices

Device slot types applicable: 
- SMARTCLEAN#ODRDTR
- SMARTCLEAN#ODRDTR_BATT_V1

Format of attribute: *"v"* in the general data format:
```json
{
  "amm": <number>  // concentration of the ammonia in the detection zone (unit depends on type of device)
  "aqi": <number>  // Air Quality Index (number between 1 - 500), only present for ODRDTR_BATT_V1
}
```
Notes:
1. *aqi* is not present in data for the type: ODRDTR
2. *amm* the value is in parts per million for ODRDTR and in parts per billion for ODRDTR_BATT_V1
3. For **more details about our air quality monitoring device** 
please visit our [help center page](https://helpcenter-smartclean.webflow.io/help-installation/od-wf-1901-how-it-works)

---

#### Example data:
For SMARTCLEAN#ODRDTR_BATT_V1

```json
{
  "t": "20211210152132",
  "v": {
    "amm": 270,
    "aqi": 180
  },
  "unixT": 1639120892,
  "DEVID": "DemoAQ1",
  "Region": "Asia/Singapore",
  "time": "2021-12-10T15:21:32+0800",
  "DevType": "SMARTCLEAN#ODRDTR_BATT_V1",
  "PID": "DemoProject",
  "InsID": "DemoLocation",
  "Display": "Demo Air Quality Light 1",
  "dow": "5",
  "month": "12",
  "hour": "15",
  "dom": "10",
  "minute": "21"
}
```

#### Example use case:
Raise an incident if value of *amm* crosses a threshold.
- *aqi* can also be used to raise an incident depending on single threshold or 
a range of AQI thresholds categorized into bands of AQI values (good to bad)

