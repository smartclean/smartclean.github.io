---
layout: default
title: Feedback device data
parent: Sensor Data
grand_parent: RealSense
nav_order: 2
---

## Data format for feedback device

Device slot type applicable:
- SMARTCLEAN#FD

Format of attribute: *"v"* in the general data format:
```json
{
  "n": 1, // Feedback nature (Positive / Negative). Value of "1" means negative, otherwise Positive.
  "rating": 1, // Feedback rating number (usually, 1 - 5)
  "nm": "Excellent", // Feedback rating name - human readable name for the rating number (set in the configuration)
  "s": 3, // Feedback rating **stars** - number of stars associated to the rating (Eg: 5 stars for rating 1) 
  "reasons": {
    "ID_1": {
      "ID": "1", // ID of the feedback reason
      "Name": "Bad smell", // Name of the feedback reason
      "selector": 1 // A constant for aggregation (internal use)
    },
    "ID_2": {
      "ID": "2",
      "Name": "No toilet paper",
      "selector": 2
    }
  },
  "c": "4eccb645302e4d9c85cbace69b92d058", // ID of configuration (SlotConfig) for Device Slot in SmartClean RealSense.
  "type": "DEFECT" // Additional indicator for categorization (Eg: Feedback / Defect etc.) 
}
```
Notes:
1. Rating (*rating*) is the feedback rating provided by the user. 
   1. This value is ordered in lesser the better ordering,
      1. i.e. value of 1 indicates excellent, 2 indicates good and in this manner the value of 5 indicates very bad.
   2. This results in a standard metric emission of *sg.smartclean.fd.raw.rating*.
2. Stars (*s*) - Number of stars
   1. This is inverse of the feedback rating (Higher the better)
   2. To the rating value from Stars (s) and MaxRating (Forumula: SlotConfig.MaxRating + 1 - s)
3. Reasons (*reasons*) - A set of reasons selected with the bad feedback.
   1. This is meant to capture reasons for bad feedback. 
   2. Therefore, these are only present for negative feedback (i.e., data in which n = 1)
   3. This is an object containing one or more objects.
   4. Each object represents one reason and has these three attributes: _ID_, _Name_ and _selector_ 
4. Name of reason (*nm*): or nature meaning 
   1. This is the human-readable name for the rating number.

---

#### Example data:
```json
{
  "AGG": "20220905102500",
  "DASSOC": "1661754999596191547",
  "DEVID": "f4187d256b414270a4e2bc67159c118f", // Alias ID of the Device Slot
  "DevSubType": "v0",
  "DevType": "SMARTCLEAN#FD",  // Slot Type of the Device
  "Display": "User Feedbacks Foodcourt",
  "ID": "f4187d256b414270a4e2bc67159c118f",
  "InsID": "e5f3292f8d464b19baa8d3233b536b61", // ID of the Location (Zone) where the Device Slot is located.
  "PID": "9a752bdee9e64e1c80143dd27b4fd958", // ID of the Project (Building) where the Location (Zone) is present.
  "PropId": "06f98e0c4f464b84b9157b1df6adfa66", // ID of the Property to which this Project (Building) belongs to.
  "Region": "Asia/Singapore", // Standard Region of the data (IANA Timezone database name) 
  "Type": null,
  "dom": "05", // Data timestamp: day of this month
  "dow": "1", // Data timestamp: day of this week
  "expire_at": 1677896700, // time when the data expires (epoch timestamp)
  "hour": "10", // Data timestamp: hour of this day, in 24-hour format
  "minute": "25", // Data timestamp: minute of this hour
  "month": "09", // Data timestamp: month of this year
  "t": "20220905102500", // Data timestamp: Time in "YYYYMMDDHHMMSS" format.
  "time": "2022-09-05T10:25:00+0800", // Data timestamp: Time in standard ISO 8601 format.
  "unix": 1662344700, // Data timestamp: Time as epoch timestamp (upto seconds)
  "unixT": 1662344700346, // Data timestamp: Time as epoch timestamp (upto milli-seconds) 
  "utc": 1662344700, // Data timestamp: Same as epoch timestamp (UTC timezone)
  "v": {
    "c": "4eccb645302e4d9c85cbace69b92d058", // config id in realsense attached to the slot
    "n": 1, // is negative ? 1 means true
    "nm": "Excellent", //  the human readable name of the rating selected (set in config)
    "rating": 1, // the rating selected. Can be ignored in favour of s. Formula - Config.MaxRating + 1 - s
    "reasons": {
      "ID_1": {
        "ID": "1", // ID of the reason
        "Name": "Billing", // Name of the reason
        "selector": 1 // A constant for aggregation (internal use)
      }
    },
    "s": 3, // stars - note that rating is inverse of stars. Stars - higher the better. Rating - lower the better. 
    "type": "DEFECT"
  }
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


