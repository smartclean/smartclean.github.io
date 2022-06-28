---
layout: default
title: Integration based on web service queries
parent: Integrations
has_children: false
has_toc: false
grand_parent: SmartClean Matrix
nav_order: 2
---

# Integration based on web service queries
Use this option for getting information from our platform by making web requests.

Pre-requisite: 
- Any application(s) that can make web (HTTP) requests.

Outcome:
- Process (and / or store) the responses of these requests to fulfil your use case.

Our Solution:
[Matrix Web Service (API)](https://www.docs.smartclean.io/api_main.html)
- It is a collection of certain requests to our relevant services. 
- An overview is given in the section below.

#### Matrix Web Service (API)
1. **Use it for:** Querying specific information from our platform by making web https requests.
2. **Described in our docs:** https://www.docs.smartclean.io/api_main.html
3. Link to documentation for these requests is given in "Documentation" section of this docs page.
4. Examples of some requests:
    1. Get the map of locations (zones) added to your site (building).
    2. Get what device slots (sensors) are created (available) in your building or site.
       1. Additionally, filter these by provider (i.e. device slot type or the sensor type)
    3. Query past data of certain sensors in a time range.
    4. Create an incident for a location.
   
Note: These examples are described in the API documentation (point 3, above)
