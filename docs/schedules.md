---
layout: default
title: Creating Schedules
parent: Workorders
grand_parent: SmartClean Matrix
nav_order: 2
---
## Creating shifts

Shifts can be created by going to the _Schedules_ section of your dashboard.

![Schedules](https://www.smartclean.io/matrix/images/scheduleButton.png)

---

The steps involved in creating a shift are enumerated below:

1. Click on the **&#x2B;** icon in the dashboard. Note that the icon is only visible for future dates as nothing can be planned for past dates.
![Create Shift Drawer](https://www.smartclean.io/matrix/images/createShiftWebDrawer.png)

2. Start by selecting the start date time and subsequently the end date time. Note that a shift may span night hours, therefore the end time can be carried over to the next day as shown below.
![Date Selection](https://www.smartclean.io/matrix/images/dateSelection.png)

3. The shift can be allocated to one or more zones in the facility by selecting the level followed by the zone.

**Note:** The zone selection can be left empty to indicate availability of this shift as a recepient of incidents for all zones.
4. Select breaks (_optional_). Breaks are of 2 types:
  - Unplanned breaks: Specify the time allocated to this break. A person can start and end this break at any time during their shift.
  - Planned breaks: Specify the start and end time for this break. The mobile application will remind the person to start this type of break few minutes before its scheduled start time.

  **Note:** The system will not send any auto assigned incidents (IoT driven) during this duration. 
5. Add an optional description to the shift.

7. If the selected zone/s have been associated with scheduled tasks, they will appear in the right side of the application.

![Scheduling Tasks](https://www.smartclean.io/matrix/images/scheduledTasks.png)

Click on the checkbox to view the tasks inside the task group/s and select their times of occurrence.

8. Select the start and end time of the task based on how much time should one occurrence be allocated to. The system displays the minimum estimated time that should be allocated to the selected task group.

![Tasks Occurrence Times](https://www.smartclean.io/matrix/images/scheduledTasksOccurence.png)

9. If the task group for that zone is to be repeated on certain intervals, use the repeat widget to generate the task repetition times.

**Note:** The task start time is used to generate the occurrences based on the repetion duration selected.
![Tasks Occurrence Example 1](https://www.smartclean.io/matrix/images/scheduledTasksOccurenceEg1.png)

10. Select if the shift is to be repeated for certain date times based on the modes as described below:

![Shift Repeat Options](https://www.smartclean.io/matrix/images/repeatShiftOptions.png)

  - **Repeat for tomorrow**: The shift will be replicated for tomorrow's date. 
