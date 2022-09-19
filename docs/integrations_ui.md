---
layout: default
title: Links to analytical dashboards
parent: Integrations
has_children: false
has_toc: false
nav_order: 6
---

# Links to analytical dashboards
Use this option to generate web links that open analytical dashboards for your Property.

## Solution:
SmartClean embeddable BI dashboards.

## Outcome:
- BI Dashboard links can be opened from anywhere there is internet access
  - You can embed such links in your own user interfaces
  - Supplement your own reporting and BI requirements with these dashboards
- Each dashboard has a limited lifetime
- Refer to the pre-requisites below for how to setup and access this feature.

## Pre-requisites:

To set up and use such Embeddable BI dashboards in your own application:
1. Please open a support ticket with us, or
2. Contact your SmartClean account manager.

Steps for integration:
1. On-boarding - Creation of your Property.
2. Authorization - Receive credentials and steps for access.
3. Integration - Set up an environment to make requests to our BI service.
4. Validation - Open and use these dashboards.

Steps for access:
1. You can access this feature after first two steps for integration (above) are complete.
2. To get the links, make an HTTP request to our endpoint
   1. Alternatively, use our SDK for Java or Python to make this request
3. The link received in response lets you open this dashboard
4. This link is valid for at most 10 minutes. 
   1. After this duration, you need to make a request to our BI service again to generate a link.

### Screenshots

[comment]: <> (TODO - Please add screenshots)

<img alt="Screenshot 1" src="https://www.smartclean.io/matrix/images/commandCentre/commCentre1.png" width="800"/>

---
