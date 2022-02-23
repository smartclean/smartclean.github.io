---
layout: default
title: Incidents Summary Report
parent: Standard Reports
grand_parent: Reports
has_children: true
has_toc: false
nav_order: 4
---

# Incidents Summary Report

This report helps in visualizing Key performance indicators of Incidents and Tasks.<br />

It helps to track:<br />
    1. How many incidents or tasks have been generated?<br />
    2. Distribution of the incidents and tasks generated across zones, types, priorities, and statuses.<br />
    3. By whom they are generated and by whom they are resolved?<br />
    4. How many of them have been allocated to a person but not completed?<br />
    5. How many have been closed within SLA?<br />
    6. Helps in determining some of the key performance indexes of responsiveness like Average Response Time, Average Resolution Rate, and Average Resolution Time.<br />

## Helpful terminologies

**Workorder**: A workorder refers to sensor or application created incidents or scheduled tasks.<br />
**Average Response Time**: The average time taken by a person allotted to respond to the requests.<br />
**Average Resolution Time**: The average time taken by a person allotted to finish the requests.<br />
**Average Resolution Rate**: Helps in reporting how many incidents and tasks have been completed in comparison to the total generated.<br />
**Total Time Spent**: Total time taken to complete incidents as well as tasks.<br />
**SLA Violation**: SLA is violated when workorder is not completed within the stipulated time.<br />

## FAQs

1. **Do Workorders include both incidents and scheduled tasks?**<br />
Yes.

2. **Why do time interval-based graphs like “No. Of Workorders” have different time intervals depending on the interval chosen while generating the report?**<br />
It is done to facilitate easy viewing and better data ranges depending on the time interval chosen.  
- If the chosen date range is for a single day, then the data points shown are on an Hourly Basis.
- If the chosen date range is less than a month, then the data points shown are on Daily Basis.
- If the chosen date range is more than a month but less than 3 months, then the data points shown are on Weekly Basis.
- If the chosen date range is more than 3 months, then the data points shown are on a Monthly Basis.
The maximum date range is that of 190 Days for a report that can be provided.

3. **In the type of graphs mentioned in the previous question, if the date range chosen while generating the report is from 3 Jan to 15 April which means the interval of the graphs will be on monthly basis(Because the number of days is more than 3 months). In that, the data presented in “No. Of Workorders” for the month of April is for the whole of April or only till the 15th of April?**<br />
Data shown is always according to the interval provided while generating the report. Even if the column is showing April month in the time range, the data statistics shown is only till 15th of April.

## Helpful pointers for understanding some graphs:

1. “Scheduled tasks - Allocated vs Completed” graph helps in understanding how many tasks were actually allocated to be completed vs how many have been actually completed.<br />

    *Example(Graph below)*: For “2021-12-02”, Allocated tasks are 35 and Completed tasks are 25.

    ![Scheduled tasks - Allocated vs Completed](https://www.smartclean.io/matrix/images/reports/incidentsSummaryDetails/VR-1.png)


2. “Scheduled tasks - Allocated vs Completed” graph helps in understanding how many tasks were actually allocated to be completed vs how many have been actually completed.<br />

    *Example(Graph below)*: For “2021-12-02”, Allocated tasks are 35 and Completed tasks are 25.

    ![Matrix Audits](https://www.smartclean.io/matrix/images/reports/incidentsSummaryDetails/VR-2.png)

