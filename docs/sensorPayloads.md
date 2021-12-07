---
layout: default
title: Sensors Raw Data Format (Data Push or Data Lake Access)
has_children: false
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
	"unixT": 1638870783862,
	"DEVID": "<slot id>",
	"Region": "<JODA TimeZone>",
	"time": "2021-12-07T17:53:03+0800",
	"DevType": "<Type of slor>",
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
