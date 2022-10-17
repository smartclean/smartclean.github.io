---
layout: default
title: 2022-10-15
parent: Release Notes
has_children: false
has_toc: false
nav_order: 20
---

# Release notes for 2022-10-15

## Enhancements

### Improved incidents metrics report
Enhancement
{: .label .label-green }

You can now generate a heatmap of the number of incidents in this report.
Additional helpful options such as filter the incidents (group) by Zone.

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
