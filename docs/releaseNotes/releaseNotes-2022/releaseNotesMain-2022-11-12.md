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


New event type added in event bus pertaining to open incident creation as
NEW_INCIDENT_CREATED_OPEN


## 1. Enhancements and Bug-fixes


### 1.1. Group incidents and general bug fixes in FM app
Enhancement
{: .label .label-green }

1. Mobile app for FM (Facility Management) groups the incidents shown in the incidents page.
2. This release also includes minor bug fixes.

This bug has been fixed in the latest release (v62_3).


### 1.2. Get notified via Matrix event bus, when open incidents are created   
Enhancement
{: .label .label-green }

This new event can be pushed to any system via the [Matrix events push](https://www.docs.smartclean.io/eventBusCore.html)
- Note: ID of this event for the event bus is: `NEW_INCIDENT_CREATED_OPEN`
- This requires you to subscribe your system to receive the desired event via the Matrix bus

[comment]: <> (How to subscribe to this event ? Any documentation available?)
