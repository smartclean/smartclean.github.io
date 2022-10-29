---
layout: default
title: 2022-10-15
parent: Releases in 2022
grand_parent: Release Notes
has_children: false
has_toc: false
nav_order: 8
---

# Release notes for 2022-10-15

## Enhancements

### Improved incidents metrics report
Enhancement
{: .label .label-green }

You can now generate a heatmap of the number of incidents in this report.
- Additional helpful options available, such as filter the incidents (group) by Zone.

### Activate alerts from the wired air quality device based on configurable threshold for Ammonia gas.
Enhancement
{: .label .label-green }

1. Contact us, to activate alerting based on pre-configured ammonia threshold
   1. Preferably, open a support ticket with us. 
   2. Or, contact your SmartClean account manager / drop us an email. 
2. Device slot type applicable: SMARTCLEAN#ODRDTR
3. The threshold can be accessed in Matrix web, for the specific device slot under RealSense.
   1. Depending on the role associated with your Matrix user account, you can view or update this threshold.
   2. Any changes made to this threshold in Matrix web, will require 24 hours to become effective.
      1. If the change is urgent, do contact us to activate the change earlier.
4. The ammonia threshold value is defined in parts per million (ppm). "0.5 ppm" is considered an optimal threshold.

### Additional ESG widgets for embeddable BI dashboards 
Enhancement
{: .label .label-green }

New widgets catering to ESG requirements can now be added to your embeddable BI dashboards.

1. Your project must have relevant data sources available that can support these widgets. 
2. Refer to examples of widgets in relevant online documentation, link below. 
3. More information, examples and screenshots: [introducing embeddable BI dashboards](https://www.docs.smartclean.io/integrations_ui.html)
4. To learn more about or to enable this integration for your project, contact us: 
   1. Preferably, open a support ticket with us. 
   2. Or, contact your SmartClean account manager / drop us an email.

### Service desk
For internal teams and interested stakeholders to report problems easily and directly into our ticketing tool, check their status and track progress.

1.This requires signing up for a help centre account 
2. Powered by Atlassian Jira service desk. 
3. This is an additional channel, other than [SmartClean help centre](help.smartclean.io), that is already available for general use. 
4. SmartClean help centre does not require sign up, but project specific details are required for opening support tickets.

[Link to Service desk portals](https://smartclean.atlassian.net/servicedesk/customer/portals) 

## Pre-releases

Pre-release
{: .label .label-purple }

### Work Order management using the Matrix Workforce API.

Workforce management API allows you to manage unassigned and assigned work orders.

**Description:**
1. These work orders are called "_incidents_".
   1. Unassigned work orders are called _open incidents_.
   2. Assigned work orders are called _assigned incidents_.
2. Examples of incident management operations (linked to API documentation):
   1. [Create new incident](https://www.apidocs.smartclean.io/workforce/incident/create-incident-without-assignee.html)
      1. This creates an open incident by default.
         1. Otherwise, you may let the system automatically assign the incident immediately after
            1. Add to the request body this key value pair: "AutoAssigned": "true"
      2. If you created an open incident, you may use the below request to assign it to your workforce member. 
   2. [Assign open incident](https://www.apidocs.smartclean.io/workforce/incident/assign-incident.html)
   3. [Start open incident](https://www.apidocs.smartclean.io/workforce/incident/start-open-incident.html)
   4. [End open incident](https://www.apidocs.smartclean.io/workforce/incident/end-open-incident.html)
3. Requests for incident management are grouped under the SC Teams (_scteams_) module.
   1. You can see this in the name of each operation 
      1. i.e., value of query parameter: "op" in each of these requests
      2. For example `scteams.assignIncident` where assignIncident is the request name.
4. For more details, visit: [Incidents under Workforce API documentation](https://www.apidocs.smartclean.io/workforce/incident/incident.html)

### Report and assign incidents using the Facility Management (FM) mobile app.
Pre-release
{: .label .label-purple }

FM app now allows you to report and assign incidents directly to your workforce members.

## Releases / Features
Feature
{: .label .label-blue }

### Matrix Kiosk app for mobiles and tablets

This Matrix application can run on mobile devices in Kiosk mode.

**Kiosk mode:**
1. Kiosk mode allows the app to run as a standalone application in the device.
2. Users cannot exit this mode until the admin disables the Kiosk mode. 
3. In this mode, users cannot view major UI features such as Home button, app switcher, notification tray and global actions. 
4. This mode is used to prevent the end users not tamper with the device and exit the app.

**Notes:**
This app can be installed on supported Android / Apple phones and tablets.
1. [Matrix Kiosk App in Google Play Store](https://play.google.com/store/apps/details?id=com.app.matrix_tablet_app)
2. [Matrix Kiosk App in Apple app store](https://apps.apple.com/sg/app/matrix-kiosk/id1631088978)
3. By default, this application does not require root credentials. 
4. Additional resources for installation on Android Devices:
   1. [External link to latest android apk](https://feedback-apks.s3.ap-southeast-1.amazonaws.com/mKioskv1.0.14%2B9-release.apk)
   2. [The companion Android DPC app can be downloaded here](https://feedback-apks.s3.ap-southeast-1.amazonaws.com/kiosk/utils/dpcV1.apk)
   3. [Instructions for running application in kiosk mode](https://feedback-apks.s3.ap-southeast-1.amazonaws.com/kiosk/docs/IN-Matrix-Kiosk-kiosk-mode_-181022-034210.pdf)
