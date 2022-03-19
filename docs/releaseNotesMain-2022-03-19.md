---
layout: default
title: 2022-03-19
parent: Release Notes
has_children: false
has_toc: false
nav_order: 3
---

# Release notes for 2022-03-19

Feature
{: .label .label-blue }
- All reporting services now allow for an enhanced excel download instead of default csv option earlier.

Bugfix
{: .label .label-red }
- A bug from scheduled tasks report has now been fixed where empty task groups caused the reporting service to not generate reports successfully in such edge case scenarios.


Enhancements
{: .label .label-green }
- The command center module is now available in *V2* to all properties using a system default dashboard configuration.
Reach out to your account manager if you need to get more details about this feature or need a different set of widgets.
- Relevant requests from our web services are accessible to authorised users via a Postman collection.
  - More secure authentication based on SHA-256 HMAC signing added for all requests in this collection.
    - Users may switch to this from the default (Basic) authentication using Username and Password.
  - Read about it at the [API page](/api_main.html)


Feature
{: .label .label-blue }
- The Housekeeping application now allows starting of *Adhoc* or *Unplanned* shifts directly.
To enable this feature, your property admin must define property shift definitions per day of week and assign it to the respective application user's seat.
Reach out to your account administrator to learn more about this feature activation and setup.

Pre-release
{: .label .label-purple }
- The Identity and Access Management (IAM) is now in internal preview and will be released generally to all properties at the end of March 2022 SGT.

Pre-release
{: .label .label-purple }
- The FM mobile application will be updated at the end of March 2022 SGT to allow admins to define availabilities of their members.

Pre-release
{: .label .label-purple }
- The Housekeeping mobile application will be updated at the end of March 2022 SGT to allow users to perform unplanned *Tasks* in their property.

Feature
{: .label .label-blue}
- The feature to allow Housekeeping mobile application to report incidents/defects has been released and available to all properties now.
Update your application from the respective play stores to take advantage of this feature and its associated reports.

Feature
{: .label .label-blue }
- You can now mark the attendance of your members through the *Workforce* module using the *Group Clockin*.
This feature is an add-on that is enabled on a request basis per property. Get in touch with your account manager if this feature seems important to you.

Feature
{: .label .label-blue }
- You can now define *Member Groups* for your members using the *Workforcemanagement* version **81** of the dashboard.
Member groups allow you to group your members into teams. This data is then further used by reports pertaining to attendance requirements.

Feature
{: .label .label-blue }
- You can define the property planned shifts using the *Workforcemanagement* version **81** of the dashboard.
This feature allows you to set the start and end shift hours per day of week for your property and optionally add attendance criterias per team.

Feature
{: .label .label-blue }
- Availabilities can now be defined per member using the *Availabilities* section of *Workforcemanagement* version *81*.
By defining availability of a member, you can allow them to start an un-scheduled shift from the Housekeeping mobile application.






