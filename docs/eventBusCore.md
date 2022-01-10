---
layout: default
title: Matrix Event Bus (MEB)
has_children: true
has_toc: true
nav_order: 8
---

# Matrix Event Bus (MEB)
![MEB Architecture](https://www.smartclean.io/matrix/images/Event-Bus-Architecture.png)

## What is the Matrix Event Bus ?
The purpose of Matrix Event Bus (MEB) is to stream events from various applications running in a property or organisation and deliver it to certain endpoints on a near-real time basis.
Subscribers can subscribe to a pattern (subset) or entirety of events. Billing is calculated based on the amount of data egress and certain other key parameters of deliveries.

Using MEB, third party application developers can plugin their solutions within Matrix and add value within the eco-system.
For example, an application listening to all incident creations can notify another application within their organisation about the same by subscribing to a pattern:

```json
matrix.mybuildingid.scworkforcemanagement.INCIDENT_CREATED.*
```

### What are events ?
Each application within Matrix, when it acts on certain key entities, results in a create, modify, delete or read event with respect to the namespace within that application.
For example, when a new incident is created within Matrix, its *RoutingKey* is as follows: *matrix.mybuildingid.scworkforcemanagement.INCIDENT_CREATED.HIGH*

Additionally, an event will also contain a generally complete subset of affected object's data for providing minimal information about the event.
For example, a new incident creation event will also proxy the details about the zone, name of task, who it is allocated to.
Any other information not present within the event payload can be obtained by appropriate SDK calls to Matrix.

## What events are available in the event bus ?
The following events are available on the bus.
