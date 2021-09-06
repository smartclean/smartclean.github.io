---
layout: default
title: VCS
has_children: true
has_toc: true
nav_order: 4
---

# Virtual Cleaning Supervisor (VCS)
Draft
{: .label .label-green }

## What is SmartClean VCS
*The Virtual Cleaning Supervisor is a system that generates alerts for desired events in locations where SmartClean devices are installed.*

---

**Common terms and concepts:**
1. Project
2. Installation
3. Device
4. User
6. Alert

*Project:*

    Project represents the site or location of a facility (usually a building).

*Installation:*

    Installation represents an enclosed location in the Project (usually a room).

*Device:*

    Device represents one of the main sources of data in the system. Data received by the system from devices associated to Installations is analysed to decide whether to raise Alert (and the data)

*Alert:*

    Alert conceptually represents the desired event for the system, that it wants to notify the Users. In system context, Alert can be of various types depending on the source of data, and support categories depending on custom settings for the associated Project the mode of operation.

*User:*

    User in the system context, currently represents two things: 
        (a) The Target who is expected to receive Alerts for a Location (Installation)
        (b) The special user types (eg: Attendant or Supervisor) who provide a Feedback to the system
