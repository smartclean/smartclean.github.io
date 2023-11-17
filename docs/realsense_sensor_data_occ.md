---
layout: default
title: Occupancy data
parent: Sensor Data
grand_parent: RealSense
has_toc: true
nav_order: 7
---

## Data of Occupancy Monitoring devices

### Device types applicable: 
- SMARTCLEAN#OCCMINEW (Enclosed Area Occupancy Monitoring, type 1)
- SMARTCLEAN#OCCSCM (Enclosed area occupancy monitoring, type 2)
- SMARTCLEAN#OCCDESK (Open area occupancy monitoring, type 1)

---

### Data for Enclosed Area Occupancy Monitoring, type 1 (OCCMINEW)

Format of attribute: *"v"* in the general data formats:
```json
{
   "occ": <number> // State of Occupancy (Occupied: "0", Not Occupied: "1")
}
```

---
### Data for Enclosed Area Occupancy Monitoring, type 2 (OCCSCM)

Format of attribute: *"v"* in the general data formats:
```json
{
   "occ": <number> // State of Occupancy (Occupied: "0", Not Occupied: "1")
}
```
      
### Data for Open Area Occupancy Monitoring, type 1 (OCCDESK)

Format of attribute: *"v"* in the general data format:

```json
{
   "occ": <number> // State of Occupancy (Occupied: "1", Not Occupied: "0")
}
```
   
---
### Example data:

#### OCCMINEW: Enclosed Area Occupancy Monitoring, type 1
```json
{
  "t": "20230621122532",
  "DevType": "SMARTCLEAN#OCCMINEW",
  "DevSubType": "minew",
  "time": "2023-06-21T12:25:32+0800",
  "unixT": 1687321532859,
  "Region": "Asia/Singapore",
  "DEVID": "<Alias ID of Device>",
  "v": {
    "C": "1",
    "Disass": "0",
    "Src": "x750:hz3a30e",
    "batt": 95,
    "rssi": -78,
    "occ": 1
  },
  "DASSOC": "AC233FAC7145",
  "PID": "<ID of Project>",
  "PropId": "<ID of Property>",
  "InsID": "<ID of Installation (location)>",
  "Display": "<Display name for Device>",
  "utc": 1687321532,
  "expire_at": 1702873532,
  "dow": "3",
  "month": "06",
  "hour": "12",
  "dom": "21",
  "minute": "25",
  "Type": "",
  "unix": 1687321532
}
```

#### OCCSCM: Enclosed area occupancy monitoring, type 2
```json
{
  "t": "20230621122532",
  "DevType": "SMARTCLEAN#OCCSCM",
  "DevSubType": "1",
  "time": "2023-06-21T12:25:32+0800",
  "unixT": 1687321532360,
  "Region": "Asia/Singapore",
  "DEVID": "<Alias ID of Device>",
  "v": {
    "b": "0",
    "occ": 0
  },
  "DASSOC": "FD3203B3F2",
  "PID": "<ID of Project>",
  "PropId": "<ID of Property>",
  "InsID": "<ID of Installation (Location)>",
  "Display": "<Display name of Device>",
  "utc": 1687321532,
  "expire_at": 1702873532,
  "dow": "3",
  "month": "06",
  "hour": "12",
  "dom": "21",
  "minute": "25",
  "Type": "",
  "unix": 1687321532
}
```

#### OCCDESK: Open area occupancy monitoring, type 1
```json
{
    "t": "20231117114825",
    "DevType": "SMARTCLEAN#OCCDESK",
    "DevSubType": "1",
    "time": "2023-11-17T11:48:25+0700",
    "unixT": 1700196505817,
    "Region": "Asia/Jakarta",
    "DEVID": "<Alias ID of Device>",
    "v": {
      "occ": 0
    },
    "DASSOC": "24E124600C4826953",
    "PID": "<ID of Project>",
    "PropId": "<ID of Property>",
    "InsID": "<ID of Installation (Location)>",
    "Display": "<Display name of Device>",
    "utc": 1700196505,
    "expire_at": 1715748505,
    "dow": "5",
    "month": "11",
    "hour": "11",
    "dom": "17",
    "minute": "48",
    "Type": "",
    "unix": 1700196505
  }
```
