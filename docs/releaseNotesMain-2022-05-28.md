---
layout: default
title: 2022-05-28
parent: Release Notes
has_children: false
has_toc: false
nav_order: 13
---

# Release notes for 2022-05-28


Pre-release
{: .label .label-purple }

Incidents in published or open state can now be deleted. This requires a control setting to be enabled by system administrators in their project.


Pre-release
{: .label .label-purple }

Incidents in published/pending state can be reassigned to another seat. Incidents in completed and not-resolved states can also be re-opened and assigned to another shift. These actions require some control settings to be enabled by system administrators in their project.


Feature
{: .label .label-blue }

Shift creation in workorders module is now improved. Following changes have been made:
- Date selection is not required and the system can now parse the proper date based on the times selected.
- Night shifts and tasks can be created seamlessly by just selecting times. For example a shift starting at 9PM and ending on 6AM (+1) requires you to just select shift start time and end time as 21:00 and 06:00 respectively.
- If property has defined shift timings in their settings, a dropdown is available to allow pre-selection of those times.


Enhancement
{: .label .label-green }
Audits module features enhancements to audit template creation giving you more flexibility to mark answers as default and allowing creation of templates that are applicable to more than one zone category or all zones in the property. This multi-selection allows a single template to be used across zones which was earlier not the case and required creation of one template per zone category.


Enhancement
{: .label .label-green }
Property level availabilities and shift timings can now define times spanning next day hence allowing availabilities to be defined across days.
