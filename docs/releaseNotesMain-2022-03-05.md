---
layout: default
title: 2022-03-05
parent: Release Notes
has_children: false
has_toc: false
nav_order: 1
---

# Release notes for 2022-03-05

Feature
{: .label .label-blue }
- Two new reporting services are now available in production, namely, *Incidents Tabular Report* and *Scheduled Tasks Tabular Report*. The reports feature PDF and Excel downloads with and without images.
The reports allow property owners to get an immediate historical list of tasks performed or faults rectified along with images taken during such events.

Feature
{: .label .label-blue }
- Oracle module or the command center view has now graduated to beta and is expected to be available in general availability in the next release.
Oracle module features advanced dynamic dashboarding and white labelling or co-labelling options.

Enhancements
{: .label .label-green }
- Enhancements to reporting services *Incidents Summary* wherein open state incidents are also used towards certain KPI presented.
Open incidents refer to incidents that could not be auto-allocated by the system or were not allocated by the users during their reporting.

Enhancements
{: .label .label-green }
- Grids dashboard now highlights only those zone categories on the left navigation that have at least one zone defined.

Feature
{: .label .label-blue }
- Member group creation feature has now graduated to beta and is expected to be available in the next release.

Pre-release
{: .label .label-purple }
- Feature to start ad hoc shifts is now in beta and is expected to be available in the next release along with options to define availabilities of team members.

Bugfix
{: .label .label-red }
- A bug causing the web reports to not send an email on generation has now been fixed.

Enhancements
{: .label .label-green }
- Workforce management API now allows you to query all planned shifts across the entire property. This is in addition to the existing API that queries the same per building.
