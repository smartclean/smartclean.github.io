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

**Pre-requisite:**
- Any application(s) that can make web (HTTP) requests.

**Outcome:**
- Process (and / or store) the responses of these requests to fulfil your use case.

**Our Solution:**
[Matrix Web Service (API)](https://www.docs.smartclean.io/api_main.html)
- It is a collection of certain requests to our relevant services. 
- An overview is given in the section below.

#### Matrix Web Service (API)
1. **Use it for:** Querying specific information from our platform by making web https requests.
2. **Introduced in our documentation at:** [Matrix Web Service (API)](https://www.docs.smartclean.io/api_main.html)
3. All supported requests to our services are described in this 
[API documentation here](https://documenter.getpostman.com/view/2593073/UVsPQ4vL)
4. **Examples of some requests:**
    (Along with link to API documentation for each)
    1. Get the map of locations (zones) added to your site (building)
       - Service (folder): [Grids](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#974fff54-1dad-4ff1-a384-093bed250a0a)
       - **Request:** [get Zones map](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#8e3459df-6c35-40c3-9420-2d145aa73df5)
    2. Get what _Device Slots_ (sensors) are created (available) in your building or site.
       - Service (folder): [Device Management](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#77a77df0-8c11-42da-ab79-624a40c33427)
       - **Request:** [get all for Building](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#5c397bba-5610-45d5-ba9a-b194dc52b192)
       - Additionally, filter _Device Slots_ available by provider (i.e. device slot type or the sensor type)
         - **Request:** [get all for Building by Provider](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#aacf5d9d-963a-4e54-b89a-bdd2e705cc79)
    3. Query past data of certain sensors in a time range.
       - Service (folder): [Metrics](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#9b7a698f-b18b-40aa-891d-46c5a004b387)
       - **Request:** [Get device metrics in time range](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#79b4f767-6b80-42ff-89be-8b6043a57ff0)
    4. Create an incident for a location.
       - Service (folder): [Work Orders](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#6e96b46d-ca0a-4327-9f77-f0a9f033f57b)
       - **Request:** [report incident for Zone](https://documenter.getpostman.com/view/2593073/UVsPQ4vL#8bd85e8c-c0b2-402f-a328-1af8b84a2ec7)
