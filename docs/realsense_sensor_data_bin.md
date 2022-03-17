---
layout: default
title: Bin monitoring device data
parent: Sensor Data
grand_parent: RealSense
nav_order: 4
---

## Data format for bin monitoring devices
Device slot type applicable:
- SMARTCLEAN#BIN

Format of attribute: *"v"* in the general data format:
```json
{
  "p": <number> // Percentage from 0 to 100
}
```

**Notes:**
1. Where, *p* represents the empty space (remaining) inside the enclosing bin container
2. For **more details about our bin level monitoring devices** 
please visit our [help center page](https://helpcenter-smartclean.webflow.io/help-installation/how-it-works)

---

#### Example data:
For bin container level monitoring device type:
- SMARTCLEAN#BIN

```json
{
  "t": "20211210152132",
  "v": {
    "p": 15.5
  },
  "unixT": 1639120892,
  "DEVID": "DemoBin1",
  "Region": "Asia/Singapore",
  "time": "2021-12-10T15:21:32+0800",
  "DevType": "SMARTCLEAN#BIN",
  "PID": "DemoProject",
  "InsID": "DemoLocation",
  "Display": "Demo Bin 1",
  "dow": "5",
  "month": "12",
  "hour": "15",
  "dom": "10",
  "minute": "21"
}
```

#### Example use case:
Raise an incident if the value of *p* reaches below a certain minimum threshold.
This indicates that the bin container is near to getting full.

