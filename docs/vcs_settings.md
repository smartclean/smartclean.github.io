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

## Important Settings for Solutions and Work Orders
*Out of all available settings that affect Work Orders created by SuperSense, there are few that are of interest*

### Settings affecting Work Order generation for all Solutions
*Work Order generation settings will allow you to configure the criteria for generation of Work Orders for all Solutions.*

- Work Order cool down duration for a Location:
    
  - *This setting controls the rate at which Work Orders are created for a Location.*
    - When a Work Order is created for a Location, all work orders are blocked from being created for this duration after the last work order was created.
    - The purpose of the setting is to prevent too many work orders from being repeatedly created for a location.

### Settings affecting Work Order generation for specific Solutions
*Solution specific settings will allow you to configure the criteria for generation of Work Orders for that Solution.*

- [Settings for Air Quality Monitoring Solution](/vcs_aq_settings.html)
- [Settings for Usage Monitoring Solution](/vcs_pc_settings.html)
- [Settings for Bad Feedback Reporting Solution](/vcs_fd_settings.html)
- [Settings for Consumable Monitoring Solution](/vcs_cmd_settings.html)
- [Settings for Bin Monitoring Solution](/vcs_bin_settings.html)