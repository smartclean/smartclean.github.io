---
layout: default
title: Attendance Status By Planned Shifts
parent: Standard Reports
grand_parent: Reports
has_children: true
has_toc: false
nav_order: 1
---

# Attendance Status By Planned Shifts.

This report helps in the calculation of how many people were present across the planned shifts defined. If designation data is provided, it helps to visualise how many people were present in a particular shift belonging to a particular designation.

## Helpful terminologies:

**ActualCheckInTime**: When a person actually Clocked-In and started their shift.<br />
**ActualCheckOutTime**: When a person actually Clocked-Out and ended their shift.<br />
**ExpectedCheckInTime**: The pre-defined shift allotted Check-In time, that is, when the person is expected to start the shift.<br />
**ExpectedCheckOutTime**: The pre-defined shift allotted Check-Out time, that is, when the person is expected to end the shift.<br />
**Actual Shift**: The time interval between ActualCheckInTime and ActualCheckOutTime.<br />
**Shift**: The time interval between ExpectedCheckInTime and ExpectedCheckOutTime.<br />

## Notes:

- For calculating we always consider *ActualCheckInTime* and *ActualCheckOutTime*. But If a person has not Clocked-Out then for appropriate calculation of durations, it is considered as equal to the *ExpectedCheckOutTime*.

- If the *ACTUAL_CLOCK_OUT* event is not being sent at all, in that case, a “Default Clock Out interval” can be set which is 8 hours by default but can be edited depending on the requirement. It means - *ActualCheckOutTime* = *ActualCheckInTime* + “Default Clock Out interval”.

## Visual Representation for determining Attendance Status:

1. If a person has Clocked-In before the shift starts but Clocked-Out within the shift. The person is considered as present in that shift.<br />
    
    Example: The person’s *Actual Shift* is from 19th Jan 7:00 AM to 19th Jan 10:00 AM and *Shift* is from 19th Jan 8:00 AM to 19th Jan 11:00 AM. In this case, the person is considered as present within the *Shift*.

    ![VR-1](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-1.png)

2. If a person falls in neither of the shifts defined, they will not be considered as present in any shift.<br />

    Example: The person’s *Actual Shift* is from 19th Jan 6:00 AM to 19th Jan 7:00 AM and *Shift* is from 19th Jan 8:00 AM to 19th Jan 11:00 AM. In this case, the person is considered Absent.

    ![VR-2](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-2.png)

3. If a person Clocked-In before shift 1 started and Clocked-Out in shift 2 which is after shift 1. Then the person will be considered present in both shifts.<br />
    
    Example: The person’s *Actual Shift* is from 19th Jan 7:00 AM to 19th Jan 12:00 Noon and the two pre-defined *Shifts* are from 19th Jan 8:00 AM to 19th Jan 11:00 AM and 19th Jan 11:00 AM to 19th Jan 2:00 PM. In this case, the person is considered present in both shifts.

    ![VR-3](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-3.png)

4. If a person Clocked-In after shift 1 started and Clocked Out in shift 2 which is after shift1. Then the person will be considered present in both shifts.<br />

    Example: The person’s *Actual Shift* is from 19th Jan 10:00 AM to 19th Jan 12:00 Noon and the two pre-defined *Shifts* are from 19th Jan 8:00 AM to 19th Jan 11:00 AM and 19th Jan 11:00 AM to 19th Jan 2:00 PM. In this case, the person is considered present in both shifts.

    ![VR-4](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-4.png)

5. If a person’s *ActualCheckOutTime* is at the precise time the *shift* starts then the person is included as present in the shift.<br />

    Example: The person’s *Actual Shift* is from 19th Jan 7:00 AM to 19th Jan 8:00 AM and *Shift* is from 19th Jan 8:00 AM to 19th Jan 11:00 AM. In this case, the person is considered Present in that shift.

    ![VR-5](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-5.png)

6. If a person’s *ActualCheckInTime* is at the precise time the shift ends then the person won’t be included in the shift.<br />

    Example: The person’s *Actual Shift* is from 19th Jan 11:00 AM to 19th Jan 1:00 PM and Shift is from 19th Jan 8:00 AM to 19th Jan 11:00 AM. In this case, the person is considered Absent in that shift.

    ![VR-6](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-6.png)

7. If a person’s *ActualCheckInTime* is the same as *ActualCheckOutTime* and it is at the precise point the *Shift* ends then the person won't be included in the shift.<br />
    
    Example: The person’s *Actual Shift* is from 19th Jan 11:00 AM to 19th Jan 11:00 AM and *Shift* is from 19th Jan 8:00 AM to 19th Jan 11:00 AM. In this case, the person is considered Absent in that shift.

    ![VR-7](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-7.png)

8. If a person’s *ActualCheckInTime* is the same as *ActualCheckOutTime* and it is at the precise point the *Shift* starts then the person will be included in the shift.<br />

    Example: The person’s *Actual Shift* is from 19th Jan 8:00 AM to 19th Jan 8:00 AM and *Shift* is from 19th Jan 8:00 AM to 19th Jan 11:00 AM. In this case, the person is considered present in that shift.

    ![VR-8](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-8.png)

9. If a person has Checked In the previous day and his/her/their shift extends to the next day and they fall within the two shifts range following the points above. In this case, the person will be considered in both shifts.<br />

    Example: The person Clocks-In on 19th Jan 7:00 PM and his *shift* starts from 19th Jan 9:00 PM to 11:59 PM. The person has to extend the shift to the other day and Clocks-Out on 20th Jan 2:00 AM. The other day shift is defined from 20th Jan 1:00 AM to 20th Jan 3:00 AM. In this case, the person is considered present in 19th Shift 9:00-11:59 as well as 20th Shift 1:00-3:00.

    ![VR-9](https://www.smartclean.io/matrix/images/reports/attendanceStatusByPlannedShifts/VR-9.png)


