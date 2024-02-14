---
layout: default
title: Temperature-Humidity data
parent: Sensor Data
grand_parent: RealSense
has_toc: true
nav_order: 9
---

## Data of Temperature-Humidity sources

### Source types applicable: 
- SMARTCLEAN#TH (Temperature-Humidity Monitoring, type 1)

---

### Data for Temperature-Humidity Monitoring, type 1 (TH)

Format of attribute: *"v"* in the general data formats:
```json
{
   "t": <number>, // Temperature in surrounding air, Unit: Degree Celcius
   "h": <number>, // Level of Relative humidity in surrounding air, Unit: Percentage (%)
}
```

---

### Example data:

#### TH: Temperature-Humidity Monitoring, type 1
```json
{
  "t": "YYYYMMDDHHMMSS",  // Time in Project timezone (YYYY: year, MM: Month, DD: Day, HH: Hour, MM: Minutes, SS: Seconds)
  "DevType": "SMARTCLEAN#TH",
  "DevSubType": "1",
  "time": "YYYY-MM-DDTHH:MM:SS+xxxx",  // Timestamp (standard format), where +xxxx indicates Project Timezone
  "unixT": 1234,  // Unix timestamp of data (milliseconds since epoch)
  "Region": "<Project region in IANA Timezone format>",  // example: "Asia/Singapore"
  "DEVID": "<Alias ID of Device>",  //  Identifies the device in our system.
  "v": {
    "t": 24.7, 
    "h": 13.4
  },
  "DASSOC": "",  // Some ID from our system
  "PID": "<ID of Project>",  // Identifies the Building in our system
  "PropId": "<ID of Property>",  // Identifies the Property in our system
  "InsID": "<ID of Installation>",  // Identifies the location (zone) in our system
  "Display": "<Display name for Device>",
  "utc": 1,  // Unix timestamp of data (seconds since epoch)
  "expire_at": 9,  // Unix timestamp of expiry (seconds since epoch)
  "dow": "6",  // Day of week (where 1 represents Monday and 6 represents Saturday.)
  "month": "12",  // Month number (01-12)
  "hour": "24",  // Hour of day (00 to 24)
  "dom": "31",  // Day of month (01 to 31)
  "minute": "59",  // Minutes of hour (00 to 59)
  "Type": "",  // Not applicable.
  "unix": 1  // Unix timestamp of data (seconds since epoch)
}
```