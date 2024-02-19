---
layout: default
title: Incidents Push
parent: Matrix Event Bus (MEB)
grand_parent: SmartClean Matrix
nav_order: 2
---

## Receive Workforce incidents (work orders)
This page describes how workorders generated in Matrix can be pushed to your web endpoint over https.


## How it works
1. Given a valid URL to an available web service, we can enable Matrix incidents generated in your Property or Building to be pushed to this endpoint in batch.
   
2. Here, batch means a collection of data objects, where each object represents an incident (work order).

3. We recommend securing your web service with some form of authentication.
   1. So that only your authorised clients (such as our matrix event bus) can make requests to it.
   2. Authentication schemes that Matrix event bus can currently work with:
      1. Basic (based on username, password)
      2. OAuth (with grant type: client credentials)
      3. OAuth (with grant type: refresh token)
      4. Authentication for _Azure Event Hub_ or _AWS IoT_ 
   
4. Please ensure the protocol used for the web service is HTTP secure 
   - i.e HTTPS instead of HTTP

## Pre-requisites to enable data push
1. Property created for your Matrix account.
2. Valid data sources for Matrix incidents installed and activated in this Property.
3. Valid HTTPS URL to your available web service to receive the incidents.
   

### Example use case:
Using Matrix incidents pushed to your application, you may fulfil or enhance your own use cases.
- Such as, but not limited to:
1. Perform actions based on each new Matrix incident received.
2. Create or enrich your own digital user interfaces
3. Create or enhance your own data processing and visualisation applications.
4. Design APIs for users of your application to query.


### Example of open incident pushed via Matrix Event Bus

Note: Any incidents pushed using Matrix Event Bus will follow the "General Data Format" described in the parent page.

 ```json
  [
   {
    "ID": "<Building ID>",  // ID of Building in your Property for which this Incident created.
    "ATTR": "<Event ID>#<Suffix>", //  internal use.
    "Description": "<Event Description>",
    "Event": "<Event ID>",
    "Principal": "<Building ID>",  // ID of Principal to which this Entity belongs (building or property)
    "PType": "building",  // Type of Principal configured (building or property)
    "Entity": "<Property ID>",  // ID of Entity to which this incident for (building or property)
    "EType": "property",  // Type of Entity configured (building or property)
    "RoutingKey": "matrix.<Principal>.<Matrix Module ID>.<Event ID>.<Priority>",
    "RoutingKeyS": [
      "matrix",
      "<Principal>",
      "<Matrix Module ID>",
      "<Event ID>",
      "<Event Priority>"
    ],
    "Status": "<Event Priority>",
    "Time": "<Matrix Module ID>#<seconds since unix epoch>",
    "UnixTime": "<seconds since unix epoch>",
    "UnixTimeInt": 1,  // seconds since unix epoch as a number
    "Module": "<Matrix Module ID>",
    "Meta": {
      "AEnd": 0,  // Time (seconds since epoch) when incident action was completed (applies to Assigned Incidents)
      "AStart": 0,  // Time (seconds since epoch) when incident action was started (applies to Assigned Incidents)
      "By": "<Incident Type>", // Source of Incident (Example: Sensor type)
      "End": 901, // Time (seconds since epoch) when time for acting on incident is over (i.e. incident reached its due time)
      "EscalationLevel": "L0",  // Escalation level example: L0/L1/L2 (for more, refer to page on Escalation Policy)
      "Name": "<Incident Name>",  // Name of incident
      "Priority": "<Priority ID>",  // Identifier for incident Priority (eg "H" for Priority = "HIGH")
      "SourceDeviceIdentifier": ["<Source Entity ID>"], // IDs of Sources creating this Incident (example: Alias IDs of Sensors)
      "Start": 1,  // Time (seconds since epoch) when incident was created or assigned (if it was assigned)
      "Status": "<Incident Status>", // State in which the Incident is currently in.
      "TaskId": "1686793261034749182",  // ID of Task associated to this Incident
      "Type": "<Workforce Entity ID>",  // For example: INCIDENT or TASK
      "Zone": "<Zone ID>",  // ID of Zone (location) of the Incident creating source.
      "ZoneName": "<Zone Name>" // Name of Zone (location) of the Incident creating source.
    }
  }
]
 ```