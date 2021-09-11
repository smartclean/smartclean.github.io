---
layout: default
title:  Air Quality Monitoring Solution (Settings)
parent: SuperSense Settings
grand_parent: SuperSense
nav_order: 2
---

# Air Quality Monitoring Solution Settings
*Settings to configure the Indoor Air Quality Monitoring Solutions active in your facility*

## What settings are available?
To configure this Solution, the following settings are available:

Configure per Device 
1. Air quality anomalies limit
    - **Type:** Maximum Threshold
    - **Description:** This threshold represents the total count of air anomalies that indicate bad air quality for a duration.
    - **Criteria to create Alert:** When the number of air quality anomalies indicated by the Device in a past duration (Below Setting: Duration to check air quality anomalies) has reached this limit.
    - **Outcome of Alert:** Notify about Bad Air Quality will be created for the location that the Device is assigned to.
2. Duration to check air quality anomalies
    - **Type:** Time Duration
    - **Description:** This represents the duration (in past, from current time) to count the number of air quality anomalies indicated by a Device.
    - **Criteria to create Alert:** When the number of air quality anomalies indicated by the Device in this duration has reached the limit (above Setting: Air quality anomalies limit).
    - **Outcome of Alert:** Notify intended users about Bad Air Quality in the location that the Device is assigned to.

Go back to [Settings for SuperSense](/vcs_settings.html)