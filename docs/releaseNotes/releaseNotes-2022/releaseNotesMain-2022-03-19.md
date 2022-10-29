---
layout: default
title: 2022-03-19
parent: Releases in 2022
grand_parent: Release Notes
has_children: false
has_toc: false
nav_order: 24
---

# Release notes for 2022-03-19

Feature
{: .label .label-blue }
- **Matrix** has two new features. 

1. **Matrix Command Centre**: Now, you get live updates on-screen without bouncing through different modules. It gives you birds-eye visibility with KPIs from the modules in a single place. Customise it at any time to fit the requirements. You can co-label or white label the platform for better personalisation.  
Video Link: [https://vimeo.com/693415733](https://vimeo.com/693415733)

2. **Configure availability in Matrix**: Admins can now indicate employees' availability via *Matrix* (web and mobile app). It is then displayed in the schedule, enabling the planner to consider it while assigning shifts and tasks. Availability is a kind of ad-hoc shift without any impact of delayed shift & absent shift. It is for properties with higher prioritisation for workorder resolution irrespective of workforce attendance. It removes the burden of creating zones and scheduling tasks.  
Video Link: [https://vimeo.com/693418798](https://vimeo.com/693415733)

    To start, the person with valid access should configure the shift hours and shift day mapping available under the settings tab of the workforce module.  
    a. *Shift Day Mapping*: It defines the scope of a shift with its duration, start and end time, and the required workforce. This scoping may vary from day to day, and *Matrix* allows you to configure it individually.  
    b. *Shift hours*: The working duration of facility management services based on the property's working hours. 

    The cleaner can clock in through their HK app. They can subsequently complete all tasks allocated to them during these availability hours.  

Feature
{: .label .label-blue }
- **Incidents Tabular Report**: New Feature  

This report showcases all reported incidents at your property at a table. You can quickly filter this data with multiple options and export it to pdf/excel. All supporting documents added to the incident can be visible as an attachment. 

![Incidents Tabular Report](https://www.smartclean.io/matrix/images/Incidents-Tabular-Report.png)


Feature
{: .label .label-blue }
- **Scheduled Task Tabular Report**: New Feature 

It represents the list of all scheduled tasks performed at the property. You can quickly filter this data with multiple options and export it to pdf/excel. A list of scheduled but not completed tasks are currently not available in this report.  

![Scheduled Task Tabular Report](https://www.smartclean.io/matrix/images/Scheduled-Task-Tabular-Report.png)

Enhancements
{: .label .label-green }
- **Open issues in Reports**: Improvements 

Open issues are now counted in the reports and added as a KPI. Open issues do not affect the average response and resolution times. 

Feature
{: .label .label-blue }
- **Teams**: New Feature  

It is a collection of people based on skill, responsibility, service or location.  

![Teams](https://www.smartclean.io/matrix/images/Open-issues-in-Reports.png)

Feature
{: .label .label-blue }

- **Housekeeping app** has two new features. 

1. The *HouseKeeping app* now allows all clocked-in users to start scheduled tasks if its available under the open tasks tab. Previously, the cleaners were allowed to work on assigned tasks only.  

2. Any user with *HouseKeeping app* can report an incident via the app. Auto allocation does not work here. The manager can verify the issue and assign to available workforce through web or FM app. 

API Documentation: For any type of integration, get the details from the API documentation. [https://www.docs.smartclean.io/api_main.html](https://www.docs.smartclean.io/api_main.html)

Feature
{: .label .label-blue }
- You can now mark the attendance of your members through the *Workforce* module using the *Group Clockin*.
This feature is an add-on that is enabled on a request basis per property. Get in touch with your account manager if this feature seems important to you.


Bugfix
{: .label .label-red }
- A bug from scheduled tasks report has now been fixed where empty task groups caused the reporting service to not generate reports successfully in such edge case scenarios.

Enhancements
{: .label .label-green }
- Relevant requests from our web services are accessible to authorised users via a downloadable Postman collection.

More secure authentication based on SHA-256 HMAC signing added for all requests in this collection.
Users may switch to this from the default (Basic) authentication using Username and Password.

Read more details about it at the [API page](/api_main.html).

Pre-release
{: .label .label-purple }
- The Identity and Access Management (IAM) is now in internal preview and will be released generally to all properties at the end of March 2022 SGT.

Pre-release
{: .label .label-purple }
- The FM mobile application will be updated at the end of March 2022 SGT to allow admins to define availabilities of their members.

Pre-release
{: .label .label-purple }
- The Housekeeping mobile application will be updated at the end of March 2022 SGT to allow users to perform unplanned *Tasks* in their property.


