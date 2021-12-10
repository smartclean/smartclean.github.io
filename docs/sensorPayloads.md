---
layout: default
title: Sensors Raw Data Format (Data Push or Data Lake Access)
has_children: true
has_toc: true
nav_order: 7
---
# General Data Format
The raw data from sensors is accessible when third party push is enabled in RealSense for a property or through a dedicated provisioned data lake.
The generic data format is:

```json
{
  "t": <string>,  // Timestamp in string format: yyyymmddhhmmss, yyyy=year, mm=month, dd=day
  "v": <custom type>  // Realtime Data from Sensor depending on the type of the Sensor
  "unixT": <number>  // Unix time in milliseconds
  "DEVID": <string>,  // Slot ID for the Device
  "Region": <string>,  // Timezone string in JODA format (See reference at bottom of page)
  "time": <string>,  // Timestamp in string format: YYYY-MM-DDTHH:mm:ss+offset
  "DevType": <string>,  // Type of the Device Slot (Example: PC for People Counter, FD for feedback etc).
  "PID": <string>,  // ID of the Project.
  "InsID": <string>,  // ID of the Location / Zone where the Device Slot is located.
  "Display": <string>,  // Name of the Device Slot (for identification)
  "dow": <string>,  // Day of Week - 0: Sun to 5: Sat
  "month": <string>,  // Month of the year (1 - 12)
  "hour": <string>,  // Hour of day (0 - 23)
  "dom": <string>  // Day of month (0 - 31)
  "minute": <string>  // Minute of the Hour (0 - 59)
}
```

## Type of Device Slot (DevType)
The type of a device slot follows a certain format. 
The generic format is **Approved Device Provider#Predefined slot type**. 
For example, usage monitoring sensors from provider *SMARTCLEAN* have **Type** as **SMARTCLEAN#UM**.

The type of the device slot is useful for:
* Define and register standard query templates in the system for ease of access.
* Define and compute standard metrics from raw data in downstream processing engines. For example, usage monitors and people counters emit a standard metric in system pertaning to *sg.smartclean.pplctr.raw.count* depicting the usage trend of a zone over time.
* Standardise data processing ETL or batch analytics.
* Register primary KPIs and attribute their meanings over a time series of data.

## Realtime Data from Devices
This section describes the format of the custom real time data provided by the Sensor
This data is provided inside the attribute: *"v"* in the above Schema. 
The type of this data depends on the type of the standard device slot.

## Examples of Realtime Data for standard sensors by SmartClean

### Usage Monitoring Device

Device slot types applicable:
- SMARTCLEAN#PPLCTR 
- SMARTCLEAN#UM

Format of *v* in the general data format:
```json
{
  "count": <number>,  //  Number of people counted in the field of view at a time.
  "out_count": <number>  // See below, present for **SMARTCLEAN#PPLCTR** type only
}
```
Note: 
**SMARTCLEAN#PPLCTR** considers the direction, therefore, it 
provides the number of people entering the sensor's field of view in *count*
and number of people leaving the field of view in *out_count*

**SMARTCLEAN#UM** is triggered by motion, therefore it provides the number of times
people entering the sensor's field of view in *count*.

An example use case is to raise an alert when value of  *count* reaches
or crosses a maximum threshold.

An example query that returns the total people count for a time range 
across all the zones in a building is as follows:
```
select insid as Zone, sum(cast(v->>'count' as integer)) TotalPeople from <db.table>
where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#PPLCTR'
and time >= <Start Time> and time <= <End Time> group by insid;
```

### Feedback Device

Device slot type applicable: 
- SMARTCLEAN#FD

Format of *v* in the general data format:
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
Where key *rating* depicts the rating provided by the user. This results in a 
standard metric emission of *sg.smartclean.fd.raw.rating*.

The value of *rating* is ordered in lesser the better ordering, i.e.
value of 1 indicates excellent, 2 indicates good and in this manner the value
of 5 indicates very bad.

An example use case is to raise an alert when the value of *rating*
is either 4 or 5 (which indicates bad feedback).

The alert can also include the values of *reasons* that are given in the
data. Note the name of *reason* is included inside the data for the 
corresponding reason id. 

An example query that returns the average user rating for a time range across all the zones in a building is as follows
```
select insid as Zone, avg(cast(v->>'rating' as integer)) AverageRating from <db.table>
where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#FD'
and time >= <Start Time> and time <= <End Time> group by insid;
```

### Consumable and Bin Level Monitoring Devices

Device slot types applicable: 
- SMARTCLEAN#TR (Toilet Roll monitoring Device)
- SMARTCLEAN#PT (Paper Towel monitoring Device)
- SMARTCLEAN#SS (Soap Solution monitoring Device)
- SMARTCLEAN#BIN (Bin container monitoring Device)

The above types refer to: Tissue Roll, Paper Towel, Bin, Soap Solution types respectively.

Format of *v* in the general data format:
```json
{
  "p": <number> // Percentage from 0 to 100
}
```

Based on whether the device type is bin or some other consumable,
the value of *p* represents a slightly different aspect.

- For slot type **BIN**, 
  - *p* represents the empty space (remaining) inside the enclosing bin container
- For the other slot Types (TR, PT and SS),
  - *p* represents the level of consumable remaining in the container.

An example use case is to raise an alert if the value of *p* reaches
below a certain minimum threshold. If the type was bin, this indicates
that the bin container is near to getting full. For other consumable types
this indicates that the fill level of the consumable is near to getting empty.

### Spill detection device

Device slot type applicable:
- SMARTCLEAN#WD

Format of *v* in the general data format:
```json
{
  "value": <number>  // value of 1 represents spill detected.
  "AreaP": <number>  // value represents percentage of area that is wet  
}
```
An example use case is to raise an alert if the *value* is 1 and value 
of *AreaP* crosses a certain threshold

### Air Quality Monitoring Device

Device slot types applicable: 
- SMARTCLEAN#ODRDTR
- SMARTCLEAN#ODRDTR_BATT_V1

Format of *v* in the general data format:
```json
{
  "amm": <number>  // concentration of the ammonia in the detection zone (unit depends on type of device)
  "aqi": <number>  // Air Quality Index (number between 1 - 500), only present for ODRDTR_BATT_V1
}
```
Note: 
- *aqi* is not present in data for the type: ODRDTR
- *amm* the value is in parts per million for ODRDTR and in parts per billion for ODRDTR_BATT_V1

An example use case is to raise an alert if value of *amm* crosses a threshold.
*aqi* can also be used to raise an alert depending on a simple threshold or 
which range of AQI values it belongs to.

## References
JODA Timezone: https://www.joda.org/joda-time/timezones.html