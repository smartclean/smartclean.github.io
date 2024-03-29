---
layout: default
title: 2022-10-29
parent: Releases in 2022
grand_parent: Release Notes
has_children: false
has_toc: false
nav_order: 7
---

# Release notes for 2022-10-29


## 1. Enhancements and Bug-fixes


### 1.1. Fixed incorrect values in incidents heatmap within the Incidents metrics report.
Bugfix
{: .label .label-red }

This bug has been fixed in the latest release (v62_3).


### 1.2. Perform inspections for your facility using the Facility Management (FM) mobile app
Enhancement
{: .label .label-green }

You can now use the FM mobile app to perform scheduled or ad-hoc inspections in your property.
- For example, refer to the screenshots section at bottom of the page.


### 1.3. Assign incidents / defects directly to member of your workforce. 
Enhancement
{: .label .label-green }

You can use the FM mobile app to now assign incidents/defects directly to a person/seat. 

Note: Earlier, this was restricted to shift based assignments only.


### 1.4. Show member group of workforce members in the Attendance - lateness report  
Enhancement
{: .label .label-green }

Attendance lateness report now adds a new column pertaining to the member group which the person belongs to (v62_3)


### 1.5. Matrix Kiosk App can be directly installed on Android devices using the APK package. 
Enhancement
{: .label .label-green }

Latest non app store version for Matrix kiosk app (v1.0.15) can be downloaded from here:

`https://feedback-apks.s3.ap-southeast-1.amazonaws.com/kiosk/mKiosk-v1.0.15.apk`


### 1.6. Shift related actions and tasks/incidents have now been de-coupled on the HouseKeeping (HK) app. 

1. HK app users can start open tasks without requiring to start shifts.
2. HK app users can also perform periodic or ad-hoc tasks without requiring to start shifts.
3. HK app users can start or report incidents without the need to start shifts.
4. This enhancement is effective since the latest release of the HK mobile app:
   1. HK mobile app version for iOS: 2.0.14.7
   2. HK mobile app version for Android: 2.0.14
   
---

## 2. Pre-releases


### 2.1. Specify time range for Embeddable BI dashboards
Pre-release
{: .label .label-purple }

BI API (apis.smartclean.bi) getSignedURL will add utility body parameter to specify various types of time ranges for the dashboard links generated.


### 2.2. Improved zone selection in Matrix Kiosk App.
Pre-release
{: .label .label-purple }

Matrix kiosk app features an improved way to allow zone selection when multiple slots/zones have been added to the application.

---

## 3. Screenshots

### 3.1. Inspection (Audit) in Facility Management mobile application

#### 3.1.1. Example 1:

<img alt="Audit in FM mobile app: example 1" src="https://www.smartclean.io/matrix/images/auditsFM-1.jpg" title="Audit in Facility Management mobile application: Example 1" width="30%"/>


#### 3.1.2. Example 2:

<img alt="Audit in FM mobile app: example 2" src="https://www.smartclean.io/matrix/images/auditsFM-2.jpg" title="Audit in Facility Management mobile application: Example 2" width="30%"/>
