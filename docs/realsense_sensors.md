---
layout: default
title: SmartClean Sensors
parent: RealSense
grand_parent: SmartClean Matrix
has_children: true
has_toc: true
nav_order: 1
---

## SmartClean Sensors and Devices
*Our devices and sensors are part of our standard solutions.*


### Device slots
Device slot represents a designated location for a certain type of device in a certain zone inside a building of your SmartClean enabled property.

**Examples** of device slots for some of our device categories are:

1. Usage monitoring devices:
   - SMARTCLEAN#PPLCTR 
   - SMARTCLEAN#UM
2. Feedback reporting device:
   - SMARTCLEAN#FD 
3. Consumable and bin level monitoring devices: 
   - SMARTCLEAN#TR (Toilet Roll monitoring Device)
   - SMARTCLEAN#PT (Paper Towel monitoring Device)
   - SMARTCLEAN#SS (Soap Solution monitoring Device)
   - SMARTCLEAN#BIN (Bin container monitoring Device)
4. Spill detection device 
   - SMARTCLEAN#WD
5. Air quality monitoring device 
   - SMARTCLEAN#ODRDTR 
   - SMARTCLEAN#ODRDTR_BATT_V1

**Please note:** 
1. Device slots are available only in zones of SmartClean enabled properties. 
   - To view and mange the zones in your building, please use the Grids service.
2. The type of device slot follows the following generic format:
   - **Approved Device Provider#Predefined slot type**. 
   - For example, our usage monitoring sensors have the device slot type: **SMARTCLEAN#UM**. 
3. The type of the device slot is useful for:
   - Define and register standard query templates in the system for ease of access.
   - Define and compute standard metrics from raw data in downstream processing engines. For example, usage monitors and people counters emit a standard metric in system pertaning to *sg.smartclean.pplctr.raw.count* depicting the usage trend of a zone over time. 
   - Standardise data processing ETL or batch analytics. 
   - Register primary KPIs and attribute their meanings over a time series of data.

   
### Raw data format
See details of the raw data format for these sensors at: [Sensors data format](/realsense_sensors_data.html)


### Firmware versions:
See details of firmware versions for these sensors at: [Sensor firmware versions](/realsense_sensor_firmwares.html) 
