---
layout: default
title: 2022-10-01
parent: Release Notes
has_children: false
has_toc: false
nav_order: 20
---

# Release notes for 2022-10-01

## New features

### Embeddable BI Dashboards
Feature
{: .label .label-blue }

1. Introduced this as a new integration option.
For more info, check this in [our online documentation here](https://www.docs.smartclean.io/integrations_ui.html):
2. Associated API is introduced under Matrix API offerings 
in [our API documentation here](https://www.apidocs.smartclean.io/matrixAPIs/matrix_api_bi_embed.html):

Note: Introduction to our integrations have been updated and can be viewed at:
[SmartClean Integrations - Overview](https://smartcleantech-my.sharepoint.com/:b:/g/personal/neel_smartclean_io/ERfj9nM7qgFHrIA46fye8P0BqA361KlZjFzBV9sSHjtMcg)

### New addition to the Workforce (scteams) API:
Feature
{: .label .label-blue }

API Operation: scteams.getTasksForPropertyByStatus
- Further details will be shared once documentation is available.

## Enhancements

### SmartClean Metrics API
Enhancement
{: .label .label-green }

1. Metrics API is useful for analytics such as querying historical data from out platform.
2. This API has been updated with various helpful requests.
3. For API details, please view [documentation for Metrics API](https://www.apidocs.smartclean.io/metricsProxy.html)
4. For more information and to understand this API, please contact us:
   1. Preferably, open a support ticket with us.
   2. Or, contact your SmartClean account manager / drop us an email.

#### Examples:

Using the following request to Metrics API:

**Request:** Get the last _n_ tasks for a Zone in _given time range_
(Default limit and time range: 10 tasks in past 24 hours)

View the [API document](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#eb1636b0-6035-4eec-be7a-7a47906059af)

### Get last task completed for a Zone by any member of workforce.

- Make this request: Get last _n_ tasks for a Zone in _given time range_ 
- Look for those task objects in which "Status" is "COMPLETED"

### Get the last incident created for a Zone and assigned to any member of workforce
- Make this request: Get last _n_ tasks for a Zone in _given time range_
- Look for those task objects in which "Status" is "PENDING"
