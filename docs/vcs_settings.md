---
layout: default
title: SuperSense Settings
parent: SuperSense
grand_parent: SmartClean Matrix
nav_order: 3
---
# SuperSense Settings

## What are the Settings for SuperSense
*Settings represent the configurable aspects for the Solutions*

Settings are organized based on the Component of the System they are applicable for, ranging from 
important high level settings to very granular less important settings.

## Important Settings SuperSense Alerts
*Out of all available settings that affect Alerts created by SuperSense, there are few that are of interest*

### Settings affecting Alert generation in a Location
*These settings will allow you to control the criteria for generation of any Alerts in a Location*

- Alert block duration for a Location:
    
  - *This setting controls the rate at which Alerts are created for a Location.*
    - When an Alert is created for a Location, all other Alerts are blocked for this duration from the time the last Alert was created.
    - The purpose of the setting is to prevent multiple Alerts from being repeatedly created for a location.
    - By default, this is set to 15 minutes, and can be configured for every Location in your facility.

### Settings affecting Alert generation for Solutions in a Location
*These settings will allow you to control the criteria for generation of Alerts of a specific type in a specific Location*

- [Settings for Air Quality Monitoring Solution](/vcs_aq_settings.html)
- [Settings for Usage Monitoring Solution](/vcs_pc_settings.html)
- [Settings for Bad Feedback Reporting Solution](/vcs_fd_settings.html)
- [Settings for Consumable Monitoring Solution](/vcs_cmd_settings.html)
- [Settings for Bin Monitoring Solution](/vcs_bin_settings.html)