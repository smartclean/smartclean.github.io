---
layout: default
title: Incidents Push
parent: Matrix Event Bus (MEB)
grand_parent: SmartClean Matrix
nav_order: 2
---

## Receive Workforce incidents (work orders)
This page describes how incidents generated for your Matrix Property can be pushed to your own application over the web.


## Pre-requisites to enable data push
1. Valid data sources for Matrix incidents installed and activated in desired Buildings of your Matrix Property (for example: IoT Sensors)
2. Valid URL to desired endpoint in your pre-available web service to receive the incidents.

       The desired endpoint in the respective web service to receive incidents must be available before requesting us to activate Incidents push.


## How it works
1. Incidents generated in your Matrix Property or desired Buildings will be pushed in batch to desired endpoint of your web service

2. We recommend securing your web service with some form of authentication. 

        In this case, provide us the authentication credentials by suitable means, along with the URL of your web service
        (for example, Username and Password if your web endpoint requires Basic access authentication)
   

### Example use case:
Using Matrix incidents pushed to your application, you may fulfil or enhance your own use cases.
- Such as, but not limited to:
1. Perform actions based on each new Matrix incidents.
2. Create or enrich your own digital user interfaces
3. Create or enhance your own data processing and visualisation applications.
4. Design APIs for users of your application to use.


### Example of incident pushed via Matrix Event Bus

Notes: 
1. Any incidents pushed using Matrix Event Bus will follow the "General Data Format" for Matrix events as described in the parent page.
2. Data in this format will be available in body of web requests made to the URL provided.
3. This example contains a single incident (JSON object) in the batch (JSON array).
4. The batch may contain more than one object, in case more than one incident was generated for your Property or Buildings at the same time.

 ```json
  [
   {
    "ID": "<Building ID>",  // ID of Building in your Property for which this Incident created.
    "ATTR": "<Event ID>#<Suffix>", //  internal use.
    "Description": "<Event Description>",  // Description specific to this event (example: a comment describing the Incident)
    "Event": "<Event ID>", // Identifies the kind of Matrix event (example: "INCIDENT_CREATED_OPEN" means new open incident created)
    "Principal": "<Building ID>",  // Identifies the Principal to which this Entity belongs (i.e., ID of "PType")
    "PType": "building",  // Type of Principal configured (building or property)
    "Entity": "<Property ID>",  // ID of Entity to which this incident for (i.e., ID of "EType")
    "EType": "property",  // Type of Entity configured (building or property)
    "RoutingKey": "matrix.<Principal>.<Matrix Module ID>.<Event ID>.<Priority>",  // "." separated identifiers for this event.
    "RoutingKeyS": [
      "matrix",
      "<Principal>",
      "<Matrix Module ID>",
      "<Event ID>",
      "<Event Priority>"
    ], // Routing key components enlisted.
    "Status": "<Event Priority>",  // for example: "HIGH"
    "Time": "<Matrix Module ID>#<UnixTime>",
    "UnixTime": "1",  // Timestamp (seconds since unix epoch, as string)
    "UnixTimeInt": 1,  // Timestamp (seconds since unix epoch, as number)
    "Module": "<Matrix Module ID>",  // Identifies the platform module associated with creation of this Incident, example: "scworkforcemanagement" for incidents assignable to workforce members.
    "Meta": {
      "AEnd": 0,  // Time (seconds since epoch) when incident action was completed (applies to Assigned Incidents)
      "AStart": 0,  // Time (seconds since epoch) when incident action was started (applies to Assigned Incidents)
      "By": "<Incident Type>", // Source of Incident (Example: Sensor type)
      "End": 901, // Time (seconds since epoch) when time for acting on incident is over (i.e. incident reached its due time)
      "EscalationLevel": "L0",  // Escalation level example: L0/L1/L2 (for more, refer to page on Escalation Policy)
      "Name": "<Incident Name>",  // Name of incident
      "Priority": "<Priority ID>",  // Identifier for incident Priority (eg "H" for "HIGH", "L" for "LOW" etc.)
      "SourceDeviceIdentifier": ["<Source Entity ID>"], // List of IDs of Sources creating this Incident (example: Alias IDs of Sensors)
      "Start": 1,  // Timestamp (seconds since epoch) when open incident was created (or assigned, if it was assigned to your workforce)
      "Status": "<Incident Status>", // State in which the Incident is currently in for example: "NOT_ASSIGNED" / "ASSIGNED" etc.
      "TaskId": "1686793261034749182",  // ID of Task associated to this Incident
      "Type": "<Workforce Entity ID>",  // Entity type from the Module For example: "INCIDENT" or "TASK" (for scworkforcemanagement module)
      "Zone": "<Zone ID>",  // ID of Zone (location) of the Incident creating source.
      "ZoneName": "<Zone Name>" // Name of Zone (location) of the Incident creating source.
    }
  }
]
 ```