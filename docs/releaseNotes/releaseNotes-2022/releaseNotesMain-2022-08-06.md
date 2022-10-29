---
layout: default
title: 2022-08-06
parent: Releases in 2022
grand_parent: Release Notes
has_children: false
has_toc: false
nav_order: 11
---

# Release notes for 2022-08-06

## New features:

---

Feature
{: .label .label-blue }
- FM mobile application now allows you to add comments and add pictures to each comment for any incident or task.

Feature
{: .label .label-blue }
- Minor bug fixes and improvements to existing features in the FM application.

Feature
{: .label .label-blue }
- Housekeeping mobile application allows you to add comments and add pictures to each comment for any incident or task.

Feature
{: .label .label-blue }
- Housekeeping mobile app now allows you to require your staff to necessarily take pictures prior to closing an incident. This allows you to necessiate the business logic of pictures as proof of work.

Feature
{: .label .label-blue }
- Matrix Kiosk application has now been released in Android and iOS play stores. This application runs on all supported consumer tablet interfaces. Reach out to your account executive to learn more about this.

Feature
{: .label .label-blue }
- Matrix now allows you to seamlessly connect to a websocket endpoint for your application in a property to deliver real-time experiences to end users.

Feature
{: .label .label-blue }
- You can now develop applications in Matrix using a multitude of event sources such as - event bus, data push, application events and deliver your application within Matrix. Reach out to your account executive or enquiry@smartclean.io to know more about this feature.

Feature
{: .label .label-blue }
- VCS incorporates a new setting wherein a new alert will not be created if an existing alert exists in last N minutes.

Feature
{: .label .label-blue }
- IAM module has published new roles which allow you to achieve better control of your user accesses. For example - PropertyViewer, GridsViewer, WorkforceAdministrator. Reach out to your account executive to understand more about how to use these roles.

Feature
{: .label .label-blue }
- Matrix has certain new helper APIs now available that can be activated per property alongwith relevant quotas. For example -
 1. dynamic language translation offered by **apis.smartclean.translate**
 2. real-time TSDB queries through a rich query language offered by **apis.smartclean.tsdbmemory**
 3. real-time websocket based publish/subscribe APIs by **apis.smartclean.rtdatagateway**
 
Reach out to your account executive to enable these APIs and obtain an API key.

Enhancement
{: .label .label-green }

**Emit (Device) Slot Events**

1. Allows you to onboard controller type devices such as IoT switches, robots, etc and control them through a common interface.
2. No knowledge of the data schema is required as long as the sender sends the relevant inputs needed by RealSense for that slot.
3. RealSense performs the heavy lifting to ensure the event is emitted and delivered to relevant destinations.
    Example use case: Bad air quality event from an air quality metric: Turn on a fan and turn off when the air quality becomes good.


Enhancement
{: .label .label-green }

**Email notification for completed web reports.**

An email notification with relevant details is sent to pre-configured recipients when any requested web report 
becomes ready for viewing.

Pre-release
{: .label .label-purple }

- Matrix IAM will now allow you to define boundary permissions for your application. This is especially helpful in cases where you want your users to be limited by an upper bound while still giving them the flexibility to choose/edit their roles.

- Matrix IAM will allow you to configure your Single Sign On providers as a means to allow your existing users to access Matrix.
