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

## What events are available in the event bus ?
The following events are available on the bus.
