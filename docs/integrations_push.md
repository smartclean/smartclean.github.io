---
layout: default
title: Integration based on data push
parent: Integrations
has_children: false
has_toc: false
grand_parent: SmartClean Matrix
nav_order: 1
---

# Integration based on data push
Use this option for receiving data and events from our platform on your web service

Pre-requisite: 
- A running and secured web service (HTTPS URL) that can receive data and events from our systems.

Outcome:
- Process (and / or store) these data and events to fulfil your use cases.

Our Solutions:
1. [Sensor data push](https://www.docs.smartclean.io/realsense_data_push.html)
2. [Matrix events push](https://www.docs.smartclean.io/eventBusCore.html)

An overview of these are given in the below sections.

---

## Sensor data push
1. **Use it for:** receiving batches of raw sensor data in near real time on your web service (HTTPS endpoint)
2. **Described in our docs:** https://www.docs.smartclean.io/realsense_data_push.html
3. Examples of some data:
   1. Feedback rating data
   2. Air quality sensor data
   3. People counter sensor data
   4. Other sensor data (like consumable or bin monitoring)
4. Sensor types and data format are described  

## Matrix event push (Matrix Event Bus)
1. **Use it for:** receiving specific events from Matrix in near real time on your web service (HTTPS endpoint)
2. **Described in our docs:** https://www.docs.smartclean.io/eventBusCore.html
3. Examples of some events:
   1. Zone created:
      1. Zone is a location in your site (building)
      2. This means a zone was defined and added in your building.
   2. Task started / completed
       1. This means a planned or scheduled activity has been started or completed by someone who was assigned to it.
       2. From this you can infer the last clean time- i.e. when a cleaning activity was started and completed- Since a cleaning activity is created as a task in our system.
   3. Incident created 
       1. This means an issue was created
       2. Either by some supervisor or by a sensor
   4. Incident started / completed
       1. This means work was started on an issue and then completed.
       2. By someone who was assigned to the issue 
4. These examples are listed in a section at the bottom of this docs page
   - This section is called: 'What events are available in the event bus'

---

## Difference between Matrix events push and Sensor data push:
1. For the user of these two services, both behave the same, i.e. both send data to a web service (HTTPS endpoint)
2. Since sensor data can be quite voluminous as compared to Matrix events, sensor data push is activated separately from other events.
