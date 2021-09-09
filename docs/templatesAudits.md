---
layout: default
title: Creating Inspection Templates
parent: Audits
grand_parent: SmartClean Matrix
nav_order: 1
---
# Creating inspection templates

Inspection templates can be defined by going to the _Templates_ section of your dashboard.

![Templates](https://www.smartclean.io/matrix/images/auditsWeb/createTemplate.png)

# What is the purpose of defining an inspection template ?

Inspection templates are _applied_ to one or more zones in your building to perform either a scheduled or unscheduled (adhoc) inspection. The main section of a template is then transformed to the following format during this process - {Zone Name} ({Building Name}).
Additionally, a reference to the zone id and building id are also created internally for future analytics.

> A template should ideally have only one main section. You can create a different template if the questions are different for same zone category (for example ground floor vs others) and combine them during scheduling.

---

The steps involved in creating an inspection template are enumerated below:

## Creating new inspection template
Click on the _Create Template_ button as shown above. Start by defining the template name, description, assign a zone category which it is applicable to and a target score between 0 and 100%.

### Add a main section to the template
