---
layout: default
title:  Air quality monitoring solution (settings)
parent: Alert settings
grand_parent: Optimus
nav_order: 2
---

# Settings for indoor air quality monitoring solution
*Settings to configure this solution after it is active in your facility*

## What settings are available?
To configure this Solution, the following settings are available:

Configure per device 
1. Air quality anomalies limit
    - **Type:** Maximum threshold
    - **Description:** This threshold represents the total count of air anomalies that indicate bad air quality for a duration.
    - **Criteria to create alert:** When the number of air quality anomalies indicated by the device in a past duration has reached this limit.
    - **Outcome of alert:** Notification about unexpected air quality will be created for the location that the device is assigned to.
2. Duration to check air quality anomalies
    - **Type:** Time duration
    - **Description:** This represents the duration (in past, from current time) to count the number of air quality anomalies indicated by a device.
    - **Criteria to create alert:** When the number of air quality anomalies indicated by the device in this duration has reached the limit.
    - **Outcome of alert:** Notify intended users about unexpected air quality in the location that the device is assigned to.

Go back to [Settings for alerts](/vcs_settings.html)
