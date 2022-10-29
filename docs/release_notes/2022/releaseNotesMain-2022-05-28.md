---
layout: default
title: 2022-05-28
parent: Release Notes
has_children: false
has_toc: false
nav_order: 89
---

# Release notes for 2022-05-28


Pre-release
{: .label .label-purple }

Incidents in published or open state can now be deleted. 
This requires a setting to be enabled by our team or any trained system administrator for your project.


Pre-release
{: .label .label-purple }

Incidents in published or pending state can be reassigned to another seat. 
Incidents in completed and not-resolved states can also be re-opened and assigned to another shift. 
These actions require some settings to be enabled by our team or any trained system administrator for your project.


Feature
{: .label .label-blue }

Shift creation in workorders module is now improved. Following changes have been made:
- Date selection is not required and the system can now interpret the proper date based on the time selected.
- Night shifts can be defined and tasks assigned to them seamlessly.
  - For example, to define a shift starting at 9PM and ending on 6AM (next day) you just need to select the 
  shift start time as 21:00 and shift end time as 06:00 respectively.
- If you already have shifts defined for your property, a dropdown list will show you these shifts 
in case you would like to choose these shifts when selecting times.


Enhancement
{: .label .label-green }
Audits module features enhancements to audit template creation giving you more flexibility to mark 
answers as default and allowing creation of templates that are applicable to more than one zone category 
or all zones in the property. 
This multi-selection allows a single template to be used across zones which was earlier not the case and 
required the creation of one template per zone category.


Enhancement
{: .label .label-green }
Property level availabilities and shift timings can now define times spanning next day hence allowing 
availabilities to be defined across days.
