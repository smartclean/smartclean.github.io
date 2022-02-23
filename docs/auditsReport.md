---
layout: default
title: Audits Report
parent: Standard Reports
grand_parent: Reports
has_children: true
has_toc: false
nav_order: 5
---

# Audits Report

This report helps in visualizing Key performance indicators of Audits that are completed.<br />

It helps to track:<br />
    1. Total number of Audits done and the average audit score.<br />
    2. Number of Auditors who performed the audits.<br />
    3. Failed and Successful Audits.<br />
    4. Helps to analyze the performance of different zones.<br />
    5. Helps to know exactly which questions failed for the Audit. Also, what are the most frequently failing questions for different zones?<br />
    6. As it is a property level report, it helps to keep a count of the number of audits performed per building and the number of zones that were inspected per building.<br />

## FAQs

1. **What is considered a Successful Audit?**<br />
When the Average Score of the Audit is greater or equal to the target score. The audit is considered as successful.<br />
And similarly, when the Average Score of the Audit is less than the target score, it is considered as a Failed Audit.

2. **Why do graphs like “Audit performance” and “Successful Audits” change their time intervals depending on the time interval chosen while generating the report?**<br />
It is done to facilitate easy viewing and better data ranges depending on the time interval chosen.
- If the chosen date range is for a single day, then the data points shown are on an Hourly Basis.
- If the chosen date range is less than a month, then the data points shown are on Daily Basis.
- If the chosen date range is more than a month but less than 3 months, then the data points shown are on Weekly Basis.
- If the chosen date range is more than 3 months, then the data points shown are on a Monthly Basis.
The maximum date range is that of 190 Days for a report that can be provided.

    *Example*: The Date Range below is 1 month. In this case, the time interval for the x-axis of the graph is on daily basis.

    ![VR-1](https://www.smartclean.io/matrix/images/reports/auditsReport/VR-1.png)
    ![VR-2](https://www.smartclean.io/matrix/images/reports/auditsReport/VR-2.png)

3. **In the type of graphs mentioned in the previous question, if the date range chosen while generating the report is from 3 Jan to 15 April which means the interval of the graphs will be on monthly basis(Because the number of days is more than 3 months). In that, the data presented in “Audit performance” for the month of April is for the whole of April or only till the 15th of April?**<br />
Data shown is always according to the interval provided while generating the report. Even if the column is showing April month in the time range, the data statistics shown is only till 15th of April.

4. **Suppose for all the zones the Average Score is 100 or above 90. What is then shown in the “Lowest Performing Zones”?**<br />
In this case nothing. We ignore the zones with an Average Score equal to or greater than 90. As it doesn’t make sense to include them in the worst list. Also, in the case of “Top Performing Zones”, we ignore the zones with an Average Score equal to or less than 50.

## Helpful pointers for understanding some graphs:

1. “Low performing inspections and failed questions/issues” table helps in understanding which audits performed the worst and what were the questions within the audit that weakened the position of the audit for a particular zone.<br />
    *Example(Graph below)*: For audit “Lift Lobbies.” and zone "East Lift Lobby L41", the average score is 75% whereas the target was supposed to be 80. "No.of Failed item(s)" denotes the number of questions that failed for an audit and "Failed Item(s)" lists the questions that failed.

    ![VR-3](https://www.smartclean.io/matrix/images/reports/auditsReport/VR-3.png)

## Words:
    Audit ↔︎ Inspection  
    Item ↔︎ Question

