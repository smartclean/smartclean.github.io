---
layout: default
title: Usage monitoring solution
parent: Solutions
grand_parent: Optimus
nav_order: 3
---
## Usage monitoring solution

### Goal
*Create an incident when the number of people entered the enclosed zone reaches a maximum limit*

---

### How does this solution work
1. Our system receives the count reported by the device installed in a zone.
2. This **count adds up over tim**e (accumulates) in the system.
3. As soon as the **count reaches the maximum limit set for the device**, an **incident is created** by the system
   1. This also **resets the accumulating counter**, so that counting again starts from 0. 
   2. For more details about this setting visit [settings for usage monitoring solution](/vcs_pc_settings.html)
4. The people counter also **gets reset** when _maintenance events_ are received by the system for a zone.
5. _Maintenance events_ include actions like acknowledge, start or end of a maintenance activity received by our system,
such as by:
   1. Cleaner logs on the Feedback tablet.
   2. Action on our Housekeeping or Attendants app.

---

### How to activate this solution
To activate this solution, install and activate SmartClean people counting sensor at a desired zone in your facility.


For **more details about our people counting device** please visit our [help center page](https://helpcenter-smartclean.webflow.io/help-installation/how-it-works-2)

---

Some of our other **solutions** which generate incidents are:
- [Indoor air quality monitoring](/vcs_aq.html)
- [Spill detection](/vcs_wd.html)
- [Feedback reporting](/vcs_fd.html)
- [Consumable monitoring](/vcs_cmd.html)
- [Bin fill level monitoring](/vcs_bin.html)
