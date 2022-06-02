---
layout: default
title: Data push
parent: RealSense
grand_parent: SmartClean Matrix
has_children: true
has_toc: true
nav_order: 3
---

# Data push
This page describes how sensor data can be sent to your web service.

## How it works
1. Given a valid URL to an available web service, we can allow data from our sensors to be 
sent in batches to this service.

2. Here, batch of data means a list of data objects, where each object represents a data point.

3. We recommend securing your web service with some form of authentication.
   1. So that only your authorised clients (such as our data push service) can make requests to it.
   2. We will need to be notified what authentication the web service requires in order to make the request accordingly.
   
4. Please ensure the protocol used for the web service is HTTP secure
   1. HTTPS, instead of HTTP


## Requirements to enable data push
1. Valid data sources (sensors in this case) correctly installed and activated in your desired locations.
   1. Our [help centre page for RealSense](https://help.smartclean.io/support/solutions/84000146848) has
information about correct installation and configuration of our sensors.
2. Valid HTTPS URL to your available web service.


## Request data and sensor data format
1. The web service will receive a _utf-8 encoded batch of JSON serialized data objects_ in the **body of the request**.
   1. Data from any sensor is sent as soon as it is received.
   2. This request body is encoded into a bytes string using the scheme: utf-8 
   3. Batch means the data is inside a list / array structure (i.e. within square brackets: [])
   4. JSON serialized data object means the data object is converted to a string (text) using JSON
2. All data objects in the batch follow the general data format described at our 
[sensor data page](https://www.docs.smartclean.io/realsense_sensor_data.html#general-data-format)
3. The custom attributes for each type of sensor are described in respective child page of our 
[sensor data page](https://www.docs.smartclean.io/realsense_sensor_data.html#custom-data-format).
   1. You can navigate to the child page for desired device slot type using the left navigation bar or 
table of contents at the bottom of this page.
4. The authentication scheme required by the web service should be notified to us in order to make the requests
with the respective authentication.

## How to understand or use this data
Following are the steps to properly extract and process the data for appropriate use.
1. Get data from body of the request
   1. This is a bytes string encoded using the scheme: utf-8
2. Decode this bytes string using the same encoding scheme (utf-8)
   1. This gives you a usable text
   2. This is the desired data batch.
3. De-serialize each string in the batch using JSON
4. Each string becomes a data object from which you can extract desired attributes.

## Example of using data:
A small subset of the actual data is described in this example.

1. You receive below data in body of request to your web service:

```
b'["{\"t\":\"20220602120301\",\"DevType\":\"SMARTCLEAN#ODRDTR_BATT_V1\"}","{\"t\":\"20220602120301\",\"DevType\":\"SMARTCLEAN#ODRDTR_BATT_V1\"}"]'
```

2. Decode this using utf-8, you get:

```
["{"t":"20220602120301","DevType":"SMARTCLEAN#ODRDTR_BATT_V1"}","{"t":"20220602120301","DevType":"SMARTCLEAN#ODRDTR_BATT_V1"}"]
```

3. De-serialize each string in this list / array using JSON
   (If there is more than 1 string in this list, you may iterate over each)
   1. De-serialize the first string in the batch, you get:
       ```
          {"t":"20220602120301","DevType":"SMARTCLEAN#ODRDTR_BATT_V1"}
       ```
   2. De-serialize the second string in the batch, you get:
       ```
       {"t":"20220602120301","DevType":"SMARTCLEAN#ODRDTR_BATT_V1"}
       ```
   3. Each object contains various attributes, which you can use. 
   For example, value of "DevType" indicates what is the slot type of the sensor / device. 
   Value of "t" is the timestamp string in YYYYMMDDHHMMSS format, that is local to the timezone
   (which is indicated in attribute: "Region")
   4. Put these steps in your program and process each data to fulfil desired use cases. 
      - Examples: 
         1. If "count" inside "v" of data from PC Lite device (DevType: SMARTCLEAN#UM),
         crosses a certain maximum value, raise an alert that there is high usage. 
         2. If value of *amm* inside "v" of data from AQ Lite device crosses a certain maximum value, 
         raise an alert that there is bad smell or high ammonia concentration.
4. Some example use cases for each sensor type is mentioned at bottom each respective child page in our 
      [sensor data page](https://www.docs.smartclean.io/realsense_sensor_data.html#custom-data-format))