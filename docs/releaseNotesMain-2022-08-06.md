---
layout: default
title: 2022-08-06
parent: Release Notes
has_children: false
has_toc: false
nav_order: 18
---

# Release notes for 2022-08-06

## Enhancements

---

Enhancement
{: .label .label-green }

**Emit (Device) Slot Events**

1. Automatically perform pre-defined actions when any certain condition becomes true with any Device Slot.
2. Desired conditions are captured and generated as events by the application running for the Device Slot.
3. Example pre-defined _logical action_: send request to a service or notification to a workforce member.
4. Example pre-defined _physical action_: Turn on / Turn off your device. 
    This requires you to connect your device using our IoT Switch. 
    Example use case: Bad air quality event from the slot: Air Quality monitoring is configured to turn on a fan.


Enhancement
{: .label .label-green }

**Email notification for completed web reports.**

An email notification with relevant details is sent to pre-configured recipients when any requested web report 
becomes ready for viewing.


Enhancement
{: .label .label-green }

**New Role: Property Viewer**
1. A new system defined role has been created in Matrix.
2. Property Viewers can sign in and interact with their Properties in the Matrix web UI.
3. The platform does not allow Property Viewers to make any changes to the Property.
4. Property Viewers don't have visibility to the Workforce Management module.
   1. Since this module is not found relevant for this role.
