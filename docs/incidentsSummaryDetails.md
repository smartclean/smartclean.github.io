---
layout: default
title: Incidents Summary Report
parent: Standard Reports
grand_parent: Reports
has_children: true
has_toc: false
nav_order: 1
---

# Workorders Summary Report
This report helps in visualizing key performance indicators pertaining to actions on Incidents and Tasks.

It helps to track:

1. How many incidents or tasks have been generated?
2. Distribution of the incidents and tasks generated across zones, types, priorities, and statuses.
3. By which agent they have been generated and who resolved them?
4. How many of them have been allocated to a person but not completed?
5. How many have been closed within SLA? 
6. Helps in reporting of some key performance indexes of responsiveness such as Average Response Time, Average Resolution Rate, and Average Resolution Time.

# Helpful terminologies
*Workorder*: A workorder refers to sensor or application created incidents or scheduled tasks.
*Average Response Time*: The average time taken by a person allotted to respond to the requests.
*Average Resolution Time*: The average time taken by a person allotted to finish the requests.
*Average Resolution Rate*: Helps in reporting how many incidents and tasks have been completed in comparison to the total generated.
*Total Time Spent*: Total time taken to complete incidents as well as tasks.
*SLA Violation*: SLA is violated when workorder is not completed within the stipulated time.

# FAQs
1. Do Workorders include both incidents and scheduled tasks?
Yes

2. Why do time interval-based graphs like "No. Of Workorders" have different time intervals depending on the interval chosen while generating the report?
It is done to facilitate easy viewing and better data ranges depending on the time interval chosen.
- If the chosen date range is for a single day, then the data points shown are on an Hourly Basis.
- If the chosen date range is less than a month, then the data points shown are on Daily Basis.
- If the chosen date range is more than a month but less than 3 months, then the data points shown are on Weekly Basis.
- If the chosen date range is more than 3 months, then the data points shown are on a Monthly Basis.
