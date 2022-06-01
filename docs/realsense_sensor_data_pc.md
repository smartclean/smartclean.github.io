---
layout: default
title: Usage monitoring device data
parent: Sensor Data
grand_parent: RealSense
nav_order: 1
---

## Data format

Device slot types applicable:
- SMARTCLEAN#PPLCTR 
- SMARTCLEAN#UM (PC Lite)

Format of attribute: *"v"* in the general data format:
```json
{
  "count": <number>,  //  Number of people counted in the field of view at a time.
  "out_count": <number>  // See below, present for **SMARTCLEAN#PPLCTR** type only
  "b": "<number>" // Battery voltage (in milli volts), present for **SMARTCLEAN#UM** type only
}
```

**Notes:** 

1. **SMARTCLEAN#UM** (PC Lite)
   1. The counting is triggered purely by motion. 
   2. *count* indicates the number of times people have entered the sensor's field of view.
   3. *b* indicates the battery voltage in milli volts

2. **SMARTCLEAN#PPLCTR** 
   1. The counting considers the direction of motion.
   2. *count* indicates the number of people that have entered inside the sensor's field of view.
   3. *out_count* indicates the number of people that have moved out from the sensor's field of view.

3. For **more details about our people counting device** 
please visit our [help center page](https://help.smartclean.io/support/solutions/articles/84000347354-pc-wf-1901-how-it-works)
---

#### Example data:
- For SMARTCLEAN#UM (PC Lite)

```json
{
  "AGG": "20220601134421",
  "DASSOC": "2BC35B402C",
  "DEVID": "0f81b252335c4961991595cebe4b4ecd",
  "DevSubType": "1",
  "DevType": "SMARTCLEAN#UM",
  "Display": "Usage Monitor",
  "dom": "01",
  "dow": "3",
  "expire_at": 1669614261,
  "hour": "13",
  "ID": "0f81b252335c4961991595cebe4b4ecd",
  "InsID": "726a401e5005453d9b44d65d808a85f3",
  "minute": "44",
  "month": "06",
  "PID": "45ea1d38775046dbbdc955362b8834b1",
  "PropId": "d2ff1cc0ee104abba3a8ba030c72cd06",
  "Region": "Asia/Singapore",
  "t": "20220601134421",
  "time": "2022-06-01T13:44:21+0800",
  "Type": null,
  "unix": 1654062261,
  "unixT": 1654062261983,
  "utc": 1654062261,
  "v": {
    "b": "3000",
    "count": 1,
    "u": "6167"
  }
}
```

- For SMARTCLEAN#PPLCTR

```json
{
   "t": "20211210152132",
   "v": {
      "count": 2.0,
      "out_count": 1.0
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

#### Example use case:
Raise an incident when value of  *count* reaches or crosses a maximum threshold.
