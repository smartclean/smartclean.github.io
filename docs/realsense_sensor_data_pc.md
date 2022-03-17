---
layout: default
title: Usage monitoring device data
parent: Sensor Data
grand_parent: RealSense
nav_order: 1
---

## Data format for usage monitoring device

Device slot types applicable:
- SMARTCLEAN#PPLCTR 
- SMARTCLEAN#UM

Format of attribute: *"v"* in the general data format:
```json
{
  "count": <number>,  //  Number of people counted in the field of view at a time.
  "out_count": <number>  // See below, present for **SMARTCLEAN#PPLCTR** type only
}
```

**Notes:** 
1. **SMARTCLEAN#PPLCTR** considers the direction, therefore, it 
provides the number of people entering the sensor's field of view in *count*
and number of people leaving the field of view in *out_count*

2. **SMARTCLEAN#UM** is triggered by motion, therefore it provides the number of times
people entering the sensor's field of view in *count*.

3. For **more details about our people counting device** 
please visit our [help center page](https://help.smartclean.io/support/solutions/articles/84000347354-pc-wf-1901-how-it-works)
---

#### Example data:
- For SMARTCLEAN#PPLCTR

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

#### Example use case:
Raise an incident when value of  *count* reaches or crosses a maximum threshold.

#### Example SQL query to get raw data in time range:
An example query that returns the total people count for a time range 
across all the zones in a building is as follows:
```
select insid as Zone, sum(cast(v->>'count' as integer)) TotalPeople from <db.table>
where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#PPLCTR'
and time >= <Start Time> and time <= <End Time> group by insid;
```
