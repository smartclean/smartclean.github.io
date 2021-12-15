---
layout: default
title: Sensor data examples
parent: Sensors Raw Data Format (Data Push or Data Lake Access)
has_children: false
has_toc: false
grand_parent: SmartClean Matrix
nav_order: 2
---
## Raw data format examples for each device type.

### Usage monitoring device
- SMARTCLEAN#PPLCTR

```json
{
   "t": "20211210152132",
   "v": {
      "count": "2",
      "out_count": "1"
   },
   "unixT": 1639120892,
   "DEVID": "DemoPPLCTR1",
   "Region": "Asia/Singapore",
   "time": "2021-12-10T15:21:32+0800",
   "DevType": "SMARTCLEAN#PPLCTR",
   "PID": "DemoProject",
   "InsID": "DemoLocation",
   "Display": "Demo People Counter 1",
   "dow": "5",
   "month": "12",
   "hour": "15",
   "dom": "10",
   "minute": "21"
}
```

### Feedback reporting device
- SMARTCLEAN#FD

```json
{
   "t": "20211210152132",
   "v": {
      "rating": 3,
      "reasons": {
         "DemoReasonID1": {
            "Name": "Dirty Urinal"
         },
         "DemoReasonID2": {
            "Name": "Faulty Tap / Door Lock"
         }
      }
   },
   "unixT": 1639120892,
   "DEVID": "DemoFD1",
   "Region": "Asia/Singapore",
   "time": "2021-12-10T15:21:32+0800",
   "DevType": "SMARTCLEAN#FD",
   "PID": "DemoProject",
   "InsID": "DemoLocation",
   "Display": "Demo Feedback Tablet 1",
   "dow": "5",
   "month": "12",
   "hour": "15",
   "dom": "10",
   "minute": "21"
}
```

### Consumable monitoring device
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

### Bin monitoring device
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

### Spill detection device
- SMARTCLEAN#WD

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

### Air quality monitoring device
- SMARTCLEAN#ODRDTR_BATT_V1

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