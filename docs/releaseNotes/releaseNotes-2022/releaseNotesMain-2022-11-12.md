---
layout: default
title: 2022-11-12
parent: Releases in 2022
grand_parent: Release Notes
has_children: false
has_toc: false
nav_order: 6
---

# Release notes for 2022-11-12

## 1. Enhancements and Bug-fixes


### 1.1. Group incidents and general bug fixes in FM app
Enhancement
{: .label .label-green }

1. Mobile app for FM (Facility Management) groups the incidents shown in the incidents page.
2. This release also includes minor bug fixes.

### 1.2. Get notified via Matrix event bus, when open incidents are created   
Enhancement
{: .label .label-green }

This new event can be pushed to any system via the [Matrix events push](https://www.docs.smartclean.io/eventBusCore.html)
- Note: ID of this event for the event bus is: `NEW_INCIDENT_CREATED_OPEN`
- Contact us to subscribe your system to receive desired events via the Matrix event bus 
  - Preferably, [open a support ticket with us](https://help.smartclean.io/support/tickets/new)
  - Or, contact your SmartClean account manager.

[comment]: <> (How to subscribe to this event ? 
Will be helpful to link it here, in case viewer is insterested to know how to activate it.)
