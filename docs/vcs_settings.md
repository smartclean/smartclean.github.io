---
layout: default
title: SuperSense Settings
parent: SuperSense
has_children: true
has_toc: false
grand_parent: SmartClean Matrix
nav_order: 3
---
# SuperSense Settings

## What are the Settings for SuperSense
*Settings represent the configurable aspects for the Solutions*

Settings are organized based on the Component of the System they are applicable for, ranging from 
important high level settings to very granular less important settings.

## Important Settings for SuperSense Alerts
*Out of all available settings that affect Alerts created by SuperSense, there are few that are of interest*

### Settings affecting Alert generation in a specific Location
*These settings will allow you to control the criteria for generation of any Alerts in a Location*

- Alert block duration for a Location:
    
  - *This setting controls the rate at which Alerts are created for a Location.*
    - When an Alert is created for a Location, all other Alerts are blocked for this duration from the time the last Alert was created.
    - The purpose of the setting is to control the rate at which all Alerts are created for a Location.
    - By default, this is set to 15 minutes, and can be configured for every Location in your facility.
    - A common use case of this setting is to increase this duration to reduce the frequency of Alerts created for a Location (thus reduces total number of alerts), or reduce this duration to increase the frequency of all alerts (thus increases total number of alerts)
    - The impact of this setting is shown with the example scenario below:

      ![Alert block duration for a Location](https://www.smartclean.io/matrix/images/AlertBlockDurationForLocation.png)

### Settings affecting Alert generation in all Locations in a Facility
*These settings will allow you to control the criteria for generation of any Alerts across all SmartClean supported Locations in your Facility*

- Alert block duration for an alert type for all locations in a Facility (Optional)

    - *Controls the duration between two consecutive alerts of the same type*
      - This is an optional setting, and only works if it is set for a specific Alert type in a Location.
      - All Alerts of specific type in each Location of the Facility will only be blocked for this duration after an Alert of the same type was created.
      - This setting replaces (i.e. ignores) the Alert block duration setting applicable to all Alert types set for a Location (between alerts of the same type, in that location for which this is set).
      - The purpose of the setting is to independently control the duration between two consecutive Alerts of the same type in each Location.
      - A common use case of this setting is to increase the frequency (i.e. reduce the alert block duration) between two alerts of a same specific type (compared to the block duration that is for all alerts in each Location)
      - The impact of this setting is shown below (for a sample Location, with this setting being set for a specific Alert type in the Facility)

    ![Alert block duration for type in Locations](https://www.smartclean.io/matrix/images/AlertBlockDurationForType.png)

### Settings affecting Alert generation for Solutions in a Location
*These settings will allow you to control the criteria for generation of Alerts of a specific type in a specific Location*

- [Settings for Air Quality Monitoring Solution](/vcs_aq_settings.html)
- [Settings for Usage Monitoring Solution](/vcs_pc_settings.html)
- [Settings for Bad Feedback Reporting Solution](/vcs_fd_settings.html)
- [Settings for Consumable Monitoring Solution](/vcs_cmd_settings.html)
- [Settings for Bin Monitoring Solution](/vcs_bin_settings.html)