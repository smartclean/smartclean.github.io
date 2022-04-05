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
  "p": <number>, // Empty space remaining inside the bin container (Percentage from 0 to 100)
  "d": <number> // Distance between sensor and contents in the bin (millimeter)  
}
```

**Notes:**
1. *p* represents the empty space (remaining) inside the enclosing bin container as a percentage.
2. *d* represents the distance between the sensor and upper limit of contents in the bin container in millimeters.
3. For **more details about our bin level monitoring devices** 
please visit our [help center page](https://help.smartclean.io/support/solutions/articles/84000347349-fl-bt-2101-how-it-works)

---

#### Example data:
For bin container level monitoring device type:
- SMARTCLEAN#BIN

```json
{
  "t": "20211210152132",
  "v": {
    "p": 46,
    "d": 159 
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

