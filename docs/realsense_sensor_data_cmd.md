---
layout: default
title: Consumable monitoring device data
parent: Sensor Data
grand_parent: RealSense
nav_order: 3
---

## Data format for consumable monitoring devices

Device slot types applicable (per consumable / bin category)
1. Toilet roll / Tissue roll monitoring device:
   - SMARTCLEAN#TR
2. Paper towel monitoring device:
   - SMARTCLEAN#PT 
3. Soap solution monitoring device:
   - SMARTCLEAN#SS

Format of attribute: *"v"* in the general data format:
```json
{
  "p": <number> // Percentage from 0 to 100
}
```

**Notes:**
1. Where *p* represents the level of consumable remaining in the container.
2. For **more details about our consumable level monitoring devices** 
please visit our [help center page](https://help.smartclean.io/support/solutions/articles/84000347349-fl-bt-2101-how-it-works)

---

#### Example data:
For consumable monitoring device types:
- SMARTCLEAN#TR (Toilet Roll monitoring Device)
- SMARTCLEAN#PT (Paper Towel monitoring Device)
- SMARTCLEAN#SS (Soap Solution monitoring Device)

```json
{
  "t": "20211210152132",
  "v": {
    "p": 15.5
  },
  "unixT": 1639120892,
  "DEVID": "DemoPT1",
  "Region": "Asia/Singapore",
  "time": "2021-12-10T15:21:32+0800",
  "DevType": "SMARTCLEAN#PT",
  "PID": "DemoProject",
  "InsID": "DemoLocation",
  "Display": "Demo Paper Towel 1",
  "dow": "5",
  "month": "12",
  "hour": "15",
  "dom": "10",
  "minute": "21"
}
```


#### Example use case:
Raise an incident if the value of *p* reaches below a certain minimum threshold.
This indicates that the fill level of the consumable is near to getting empty.

