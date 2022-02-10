---
layout: default
title: Solution settings
parent: Optimus
has_children: true
has_toc: false
grand_parent: SmartClean Matrix
nav_order: 3
---

# Settings for solutions

## What are these settings
*Settings represent the configurable aspects for each solution type*

### Settings affecting incident creation for specific zone
*These settings will allow you to control the criteria for creation of incidents in specific zones*

-  Block duration for a zone:
    
  - *This setting controls the rate at which incidents are created for a zone.*
    - When an alert is created for a zone, all other incidents are blocked for this duration.
    - Purpose of this setting is to control the rate at which incidents are created for a zone.
    - By default, this is set to 15 minutes, and can be configured for every zone in your facility.
    - Examples of usage: 
      - increase this duration to reduce the frequency of incidents for a zone (thus reduces total number of incidents), 
        or reduce this duration to increase the frequency of all alerts (thus increases total number of alerts)
    - The impact of this setting is shown with the example scenario below:

      ![block duration for a zone](https://www.smartclean.io/matrix/images/AlertBlockDurationForLocation.png)

### Settings affecting incident creation for all zones in a building
*These settings will allow you to control the criteria for creation of incidents across all zones in your building*

- Block duration between incidents of a specific type for all zones in a Facility (Optional)

    - *Controls the duration between two consecutive incidents of the same type*
      - This is an optional setting, and only works if it is set for a specific incident.
      - All incidents of this type in each zone of the building will only be blocked for this duration after an incident of the same type was created.
      - This setting replaces (i.e. ignores) the block duration applicable for incident types set for a zone.
      - The purpose of the setting is to independently control the duration between two consecutive incident of the same type in each zone.
      - Example use: increase the frequency (i.e. reduce the block duration) between two incidents of the same type (compared to the block duration that is for all incidents in each zone)
      - The impact of this setting is shown below (for a sample zone, with this setting being set for a specific incident type in the building)

    ![Block duration for type in zone](https://www.smartclean.io/matrix/images/AlertBlockDurationForType.png)

### Settings affecting incidents of specific types in a zone
*These settings will allow you to control the criteria for generation of alerts of a specific type in a specific zone*

- [Settings for air quality monitoring solution](/vcs_aq_settings.html)
- [Settings for usage monitoring solution](/vcs_pc_settings.html)
- [Settings for spill detection solution](/vcs_wd_settings.html)
- [Settings for feedback reporting solution](/vcs_fd_settings.html)
- [Settings for consumable monitoring solution](/vcs_cmd_settings.html)
- [Settings for bin level monitoring solution](/vcs_bin_settings.html)
