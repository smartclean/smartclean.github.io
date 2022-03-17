---
layout: default
title: Feedback device data
parent: Sensor Data
grand_parent: SmartClean Sensors
nav_order: 2
---

## Data format for feedback device

Device slot type applicable:
- SMARTCLEAN#FD

Format of attribute: *"v"* in the general data format:
```json
{
  "rating": <number>,  // From 1 - 5
  "reasons": { // optionally present
    <reason id>: {
      "Name": <string>,  // Reason Name/Description
      "selector": <number>  // A constant for aggregation purposes
    }, ...
  }
}
```

1. Where key *rating* depicts the rating provided by the user. 
   - This results in a standard metric emission of *sg.smartclean.fd.raw.rating*. 
   - This value is ordered in lesser the better ordering, 
     - i.e. value of 1 indicates excellent, 2 indicates good and in this manner the value of 5 indicates very bad.

3. For **more details about our people counting device** please visit our [help center page](https://helpcenter-smartclean.webflow.io/help-installation/how-it-works-2)
---

#### Example data:
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

#### Example use case:
Raise an incident when the value of *rating* is either 4 or 5 (which indicates bad feedback).

Notes:
- The incident may also include the values of *reasons* that are given in the data.
- Note: *Reason name* ("Name") is included inside data for corresponding reason id (reason_id)
  - See the general format described above, 

#### Example SQL query to get raw data in time range:
An example query that returns the average user rating for a time range 
across all the zones in a building is as follows

```
select insid as Zone, avg(cast(v->>'rating' as integer)) AverageRating from <db.table>
where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#FD'
and time >= <Start Time> and time <= <End Time> group by insid;
```


