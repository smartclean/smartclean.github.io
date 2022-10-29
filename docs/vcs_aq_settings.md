---
layout: default
title:  Air quality monitoring solution (settings)
parent: Solution settings
grand_parent: Optimus
nav_order: 2
---

# Settings for indoor air quality monitoring solution
*Settings to configure this solution after it is active in your facility*

## Solution categories
Alerts from the air quality monitoring solution operate based on following two categories

**Category 1** - For air quality alerts based on anomaly detection and counting
**Category 2** - New: For air quality alerts based on ammonia threshold.

Note:
- **Category 1 is active by default** for air quality monitoring solution in your Project.
- **To switch your Project to use Category 2** for bad air quality alerts, contact us:
  - Preferably, open a support ticket with us. 
  - Or, contact your SmartClean account manager / drop us an email.


## What settings are available?
To configure this solution, the following settings are available (by category):

### Category 1 - For AQ alerts based on anomaly detection and counting

Configure per device
1. Air quality anomalies limit
    - **Type:** maximum threshold
    - **Description:** This threshold represents the total number of air quality anomalies in a certain duration.
    - **Outcome:** Incident about unexpected air quality will be created for the location that the device is assigned to.
2. Duration to check air quality anomalies
    - **Type:** time duration
    - **Description:** The duration to count the number of air quality anomalies reported by the sensor.
    - **Outcome:** Notify intended users about unexpected air quality detected recently in the zone.

### Category 2 - New: For AQ Alerts based on ammonia threshold.

Configure per device:
1. Maximum Ammonia Threshold
    - **Type:** maximum threshold
    - **Description:** This threshold represents the maximum ammonia value (undesirable level) in surrounding air.
    - **Outcome:** Incident about bad air quality will be created for the location that the device is assigned to.
    
Note: Unless Category 2 is activated for the air quality monitoring solution in your Project, Category 1 is applicable.

Go back to [solution settings](/vcs_settings.html)
