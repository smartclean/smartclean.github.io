---
layout: default
title: Links to analytical dashboards
parent: Integrations
has_children: true
has_toc: false
nav_order: 6
---

# Links to analytical dashboards
Use this option to generate web links that open analytical dashboards for your Property.

## Solution:
SmartClean embeddable BI dashboards.

## Outcome:
1. BI Dashboard links can be opened from anywhere there is internet access 
   1. You can embed such links in your own user interfaces
   2. Cross-origin request issues will not happen, since we allow any host to embed the signed URLs.
2. Supplement your own reporting and BI requirements with these dashboards

## Setup and activation:

To set up and use Embeddable BI dashboards from your SmartClean enabled Property:
1. Please open a support ticket with us, or
2. Contact your SmartClean account manager.

### Steps for integration:
1. **On-boarding** - Creation of your Property.
2. **Authorization** - Receive credentials and steps for access.
3. **Setup** - Set up an environment to make request to our BI service and use the link received in response.
4. **Validation** - Access the dashboard via the link received.

### Steps for access:
1. You can access this feature after first two steps for integration (above) are complete.
2. To receive a link to desired BI dashboard, request our BI web service.
   1. Refer to [documentation for this request here](https://www.apidocs.smartclean.io/matrixAPIs/matrix_api_bi_embed.html)

[comment]: <> (   1. Alternatively, use our SDK for Java or Python to make this request)

[comment]: <> (This request needs to be updated and refined before being added to SDK)

[comment]: <> (For users this will rather go in API docs - i.e., Activate this API and fulfil the quota for access)

3. The link received in response lets you open this dashboard
   1. This link is valid for at most 10 minutes. 
   2. After this duration, you need to make a request to our BI service again to generate a link. 
4. Each link is associated with a user session in our platform (subject quota of active sessions in your Project)

## Example _Widgets_ in a _Dashboard_
1. Project location (Map view)
2. Number of Zones in the Building (Count)
3. Usage across all Zones in past 24 hours (Bar chart)
   1. Trend of cumulative people count
4. Relative usage across all Zones in past 24 hours
   1. Trend of hourly people count
5. Last environment health across all Zones
   1. Last reported value for following parameters:
      1. Air Quality Index (if applicable)
      2. Ammonia (if applicable)
      3. Temperature
      4. Humidity
6. Air quality trend in past 8 hours for each Zone
   1. Trend for Air Quality Index
   2. Trend for Ammonia

## More examples (ESG widgets)
1. Ammonia and air quality health in last 8 hours
2. Zones with moderate or bad air quality in the last hour.
3. Tissue roll usage trends for building in last 3 days.
4. Tissue roll usage in last 24 hours across zones
5. Average tissue roll refill trends in last 4 days.
6. Heatmap of Tissue roll usage across zones.

## Frequently asked questions (FAQs)
[Visit the FAQ for Embeddable BI Dashboards here](/integrations_ui_faq.html)

---

## Screenshots

### Example dashboard 1, part 1
<img alt="Example dashboard 1, part 1" src="https://www.smartclean.io/matrix/images/BI/biEmbeddedExample1.png" width="800"/>

---

### Example dashboard 1, part 2
<img alt="Example dashboard 1, part 2" src="https://www.smartclean.io/matrix/images/BI/biEmbeddedExample2.png" width="800"/>

---

### Example dashboard 2 (with dark theme)
<img alt="Example dashboard 2 with dark theme" src="https://www.smartclean.io/matrix/images/BI/biEmbeddedExample3.png" width="800"/>

---

### ESG widgets in dashboard, Part 1
<img alt="ESG widgets in dashboard, Part 1" src="https://www.smartclean.io/matrix/images/BI/esg1.png" width="800"/>

---
### ESG widgets in dashboard, Part 2
<img alt="ESG widgets in dashboard, Part 2" src="https://www.smartclean.io/matrix/images/BI/esg2.png" width="800"/>

---
### ESG widgets in dashboard, Part 3
<img alt="ESG widgets in dashboard, Part 3" src="https://www.smartclean.io/matrix/images/BI/esg3.png" width="800"/>

---
