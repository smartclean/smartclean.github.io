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
	"DEVID": <string>,  // The Device Slot ID
	"Region": <string>,  // Timezone string in JODA format (See reference at bottom of page)
	"time": <string>,  // Timestamp in string format: YYYY-MM-DDTHH:mm:ss+offset
	"DevType": <string>,  // Type of the Device Slot (Example: PC for People Counter, FD for Feedback etc).
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

The type of the Device Slot is useful for:
* Define and register standard query templates in the system for ease of access.
* Define and compute standard metrics from raw data in downstream processing engines. For example, usage monitors and people counters emit a standard metric in system pertaning to *sg.smartclean.pplctr.raw.count* depicting the usage trend of a zone over time.
* Standardise data processing ETL or batch analytics.
* Register primary KPIs and attribute their meanings over a time series of data.

## Realtime Data from Devices
This section describes the format of the custom real time data provided by the Sensor
This data is provided inside the attribute: *"v"* in the above Schema. 
The type of this data depends on the type of the standard Device Slot.

## Examples of Realtime Data for standard sensors by SmartClean

### Usage Monitoring Solution
This represents Devices used for monitoring usage

Device Slot Types applicable: SMARTCLEAN#PPLCTR and SMARTCLEAN#UM

Format of *v* in the general data format:
```json
{
	"count": <number>,  //  Number of people counted in the field of view at a time.
	"out_count": <number>  // See below, present for **SMARTCLEAN#PPLCTR** type only
}
```
Note: 
**SMARTCLEAN#PPLCTR** considers the direction, therefore, it 
provides the number of people entering the sensor's field of view in "count"
and number of people leaving the field of view in "out_count"

**SMARTCLEAN#UM** is triggered by motion, therefore it provides the number of times
people entering the sensor's field of view in "count".

An example query that returns the total people count for a time range across all the zones in a building is as follows:
```
select insid as Zone, sum(cast(v->>'count' as integer)) TotalPeople from <db.table>
where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#PPLCTR'
and time >= <Start Time> and time <= <End Time> group by insid;
```

### Bad Feedback Reporting Solution
This represents Feedback gathering devices.

Device Slot Types applicable: SMARTCLEAN#FD

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

Usually, the ratings are ordered in lesser the better ordering.

An example query that returns the average user rating for a time range across all the zones in a building is as follows:
```
select insid as Zone, avg(cast(v->>'rating' as integer)) AverageRating from <db.table>
where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#FD'
and time >= <Start Time> and time <= <End Time> group by insid;
```

### Consumable and Bin Level Monitoring Solution 
These represent Device Slots for category of Devices that monitor fill levels in containers.

Device slot types applicable: SMARTCLEAN#TR, SMARTCLEAN#PT, SMARTCLEAN#SS, SMARTCLEAN#BIN

The above types refer to: Tissue Roll, Paper Towel, Bin, Soap Solution types respectively.

Format of *v* in the general data format:
```json
{
	"d": <number>,
	"p": <number> // Percentage from 0 to 100
}
```

Where *p* represents the percentage empty space (remaining) inside a Bin for Slot Type **BIN** 
and percentage consumable remaining for the other slot types that measure fill level.

If the "p" value reaches or goes below a minimum threshold, a corresponding alert event is raised.
Note: The minimum "p" (level) threshold is set for each Slot type belonging to this category.

### Spill Detection Solution
This refers to Device used for the Spill or Wetness Detection Solution.

Device slot type applicable: SMARTCLEAN#WD

Format of *v* in the general data format:
```json
{
	"value": <number>  // value of 1 represents spill detected.
    "AreaP": <number>  // value represents Percentage of Area that is wet  
}
```
If "value" is 1, then the Spill Detected event is raised.
Additionally, If "AreaP" is provided then this value must exceed
the minimum area threshold for the Spill Detected event to be considered,
otherwise it means that the area of the spill is insufficient.

Note: The AreaP threshold is set for the Project in general and can be specifically set for the Location as well.

### Air Quality Monitoring Solution
This refers to the Devices used for the Air Quality Monitoring Solution.

Device Slot types applicable: SMARTCLEAN#ODRDTR_BATT_V1

Format of *v* in the general data format:
```json
{
	"amm": <number>  // value of the ammonia gas component (in parts per billion)
    "aqi": <number>  // value of the standard Air Quality Index (number between 1 - 500)
}
```

"amm" and "aqi" values describe the air quality, and if the threshold 
for either or both attributes is reached, the bad air quality alert is triggered.
Note: These two thresholds are set for the Project in general and can be specifically set for the Location as well. 

## References
JODA Timezone: https://www.joda.org/joda-time/timezones.html