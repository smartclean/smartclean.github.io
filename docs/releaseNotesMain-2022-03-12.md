---
layout: default
title: 2022-03-12
parent: Release Notes
has_children: false
has_toc: false
nav_order: 2
---

# Release notes for 2022-03-12

Feature
{: .label .label-blue }
- The reporting services pertaining to attendance metrics *Attendance Status*, *Attendance Summaries*, and *Lateness Report* were being generated at a building leve.
These services have now been internally set to generate property level metrics.

Bugfix
{: .label .label-red }
- A bug from escalation policy executor where due time escalations on exact due time (0 minutes) were not being processed, has been rectified.
You can now set an escalation policy setting that allows you to notify the assignee or another person when the due time of an incident has reached.

Bugfix
{: .label .label-red }
- A bug in *open incidents* did not allow Housekeeping staff to view the attachments. This has been fixed and will be released to respective play stores.

Enhancements
{: .label .label-green }
- Oracle module is now available in *V2*. Version 2 of *Oracle* embeds capabilities to render attendance widget and fixes some bugs pertaining to auto refresh of widgets based on time.
Widgets can also specify an optional setting where they are not affected by the time duration picker explicitly, and only take the current time as it progresses.

Enhancements
{: .label .label-green }
- Open issues when allocated to someone else can take up the new start and due time in lieu of feature where housekeeping can report incidents.

Enhancements
{: .label .label-green }
- More download format options are now available in excel export of tabular scheduled tasks report.

Feature
{: .label .label-blue }
- A downloadable postman collection is now available in public domain to test out certain common APIs.
You will require a basic auth key or HMAC credentials from your property to test it.

Pre-release
{: .label .label-purple }
- The feature to allow Housekeeping mobile application to report incidents/defects has been tested and scheduled for release in the following week.
With this feature, users of Housekeeping application can report a defect and take pictures. They cannot explicitly allocate this incident to an assignee.

Feature
{: .label .label-purple }
- You can now mark the attendance of your members through the *Workforce* module.
This feature is enabled on a request basis per property. Get in touch with your account manager if this feature seems important to you.
