---
layout: default
title: Sensors Raw Data Format (Data Push or Data Lake Access)
has_children: true
has_toc: true
nav_order: 7
---
# General schema
The raw data from sensors is accessible when third party push is enabled in RealSense for a property or through a dedicated provisioned data lake.
The generic data format is:

```json
{
	"t": "20211207175303",
	"v": <variadic payload per type>,
	"unixT": <Unix time in milliseconds>,
	"DEVID": "<slot id>",
	"Region": "<JODA TimeZone>",
	"time": "<YYYY-MM-DDTHH:mm:ss+offset>",
	"DevType": "<Type of slot>",
	"PID": "<The project id>",
	"InsID": "<The location/zone id>",
	"Display": "<Name of the slot>",
	"dow": "<Day of Week - 0: Sun to 5: Sat>",
	"month": "<Month of year - 1 to 12>",
	"hour": "<Hour of day - 0 to 23>",
	"dom": "<Day of month>",
	"minute": "<Minute>"
}
```
# Type or Slot Type
The type of a slot determines multiple things and is therefore standardized. The generic format is **Approved Device Provider#Predefined slot type**. For example, usage monitoring sensors from provider *SMARTCLEAN* have **Type** as **SMARTCLEAN#UM**.
	
The type of slot can be helpful in:
* Define and register standard query templates in the system for ease of access.
* Define and compute standard metrics from raw data in downstream processing engines. For example, usage monitors and people counters emit a standard metric in system pertaning to *sg.smartclean.pplctr.raw.count* depicting the usage trend of a zone over time.
* Standardise data processing ETL or batch analytics.
* Register primary KPIs and attribute their meanings over a time series of data.

## Payload Examples
This section describes the meaning of various payload values inside the key *v* for each standard slot type.
### SMARTCLEAN#PPLCTR and SMARTCLEAN#UM
Format of *v* payload:
```json
{
	"count": <Float>,
	"out_count": <Float> // present for **SMARTCLEAN#PPLCTR** type only
}
```
Where key *count* depicts the in counted events in case of **SMARTCLEAN#PPLCTR** and sensor activations in case of **SMARTCLEAN#UM**.
An example query that returns the total people count for a time range across all the zones in a building is as follows:
>```
select insid as Zone, sum(cast(v->>'count' as integer)) TotalPeople from <db.table> where pid = '<pid>' and month = '<month>' and dom = '<dom>' and devtype = 'SMARTCLEAN#PPLCTR' and time >= <Start Time> and time <= <End Time> group by insid;
```
