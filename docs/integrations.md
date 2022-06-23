---
layout: default
title: Integrations
has_children: false
has_toc: false
nav_order: 9
---

# Integration with SmartClean Matrix
_Integrations allow you to set up access to data and events from our platform in a standard way._

## Integration mechanisms supported
1. Receive data and events from our platform on your web service.
2. Query certain information from our platform by making web requests.
3. Query data and events from an SQL database.
4. Query data from our platform by using our SDK for certain programming languages.

[comment]: <> (Should create a sub page for each of these options ? )

### 1. For receiving data and events from our platform on a web service.

Pre-requisite (what you need to have): 
- A running and secured web service (HTTPS URL) that can receive data and events from our systems.

Outcome (use case)
- Process (and / or store) these data and events to fulfil your use cases.

Our Solutions (what we provide):
1. Sensor data push
2. Matrix events push

#### Sensor data push
1. **Use it for:** receiving batches of raw sensor data in near real time on your web service (HTTPS endpoint)
2. **Described in our docs:** https://www.docs.smartclean.io/realsense_data_push.html
3. Examples of some data:
   1. Feedback rating data
   2. Air quality sensor data
   3. People counter sensor data
   4. Other sensor data (like consumable or bin monitoring)
4. Sensor types and data format are described  

#### Matrix event push (Matrix Event Bus)
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

#### Difference between Matrix Event Push and Sensor Data Push:
- For the user of these two services, both behave the same, i.e. both send data to a web service (HTTPS endpoint)
---

### 2. For getting information from our platform by making web requests.

Pre-requisite (what you need to have): 
- Any application(s) that can make web (HTTP) requests.

Outcome (use case):
- Process (and / or store) the responses of these requests to fulfil your use case.

Our Solutions (what we provide):
- Matrix Web Service (a collection of certain requests to our relevant services)

#### Matrix Web Services 
1. **Use it for:** Querying specific information from our platform
2. **Described in our docs:** https://www.docs.smartclean.io/api_main.html
3. Link to documentation for these requests is given in "Documentation" section of this docs page.
4. Examples of some requests:
    1. Get the map of locations (zones) added to your site (building).
    2. Get what device slots (sensors) are created (available) in your building or site.
       1. Additionally, filter these by provider (i.e. device slot type or the sensor type)
    3. Query past data of certain sensors in a time range.
    4. Create an incident for a location.
   
Note: These examples are described in the API documentation (point 3, above)

---

### 3. For querying data from an SQL database.

Pre-requisite (what you need to have): 
- Any means of querying a PostgreSQL database.

Outcome (use case):
- Process (and / or store) the responses of these SQL queries to fulfil your use case.

Our Solutions (what we provide):
- Dedicated database service (a collection of certain requests to our relevant services)

#### Dedicated database service
1. **Use it for:** Querying specific data from our platform using standard SQL
2. **Described in our docs:** https://www.docs.smartclean.io/dedicated-db.html
3. Example of use (after setting up this service with us)
   1. Query total people count for a time range across all zones 
   (where the device is installed) in your building.
4. Contact us when setting this up to receive:
   1. The table schema
   2. Example use cases and corresponding SQL queries
      (Based on what we use for our platform)
   3. Database connection details.
   4. Follow up, in case you want us to write data to a PostgreSQL database hosted by you.

---

### 4. For making web requests to our services using our SDK for certain programming languages.

This makes use of the Matrix Web Services to fulfil requests.

Pre-requisite (what you need to have):
- To use the SDK, you should have any application or prototype in the corresponding programming language
- The SDK needs to be downloaded and imported into your application.

Outcome (use case):
- Useful for making web requests to our services in a standard way.
- Optimised for use in the respective programming language
- Process (and / or store) the responses of these requests to fulfil your use case.

We currently have an SDK for following languages:
- Python
- Java
- Go

For example, our Python SDK is available as a release in Github:
https://github.com/hello-error/PythonSDK


