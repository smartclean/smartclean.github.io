---
layout: default
title: 2022-08-06
parent: Release Notes
has_children: false
has_toc: false
nav_order: 18
---

# Release notes for 2022-08-06

## New features:

---

Feature
{: .label .label-blue }
- FM mobile application now allows you to add comments and add pictures to each comment for any incident or task.

- Minor bug fixes and improvements to existing features in the FM application.

- Housekeeping mobile application allows you to add comments and add pictures to each comment for any incident or task.

- Housekeeping mobile app now allows you to require your staff to necessarily take pictures prior to closing an incident. This allows you to necessiate the business logic of pictures as proof of work.

- Matrix Kiosk application has now been released in Android and iOS play stores. This application runs on all supported consumer tablet interfaces. Reach out to your account executive to learn more about this.

- Matrix now allows you to seamlessly connect to a websocket endpoint for your application in a property to deliver real-time experiences to end users.

- You can now develop applications in Matrix using a multitude of event sources such as - event bus, data push, application events and deliver your application within Matrix. Reach out to your account executive or enquiry@smartclean.io to know more about this feature.

- VCS incorporates a new setting wherein a new alert will not be created if an existing alert exists in last N minutes.

- IAM module has publishes new roles which allow you to achieve better control of your user accesses. For example - PropertyViewer, GridsViewer, WorkforceAdministrator. Reach out to your account executive to understand more about how to use these roles.

- Matrix has certain new helper APIs now available that can be activated per property alongwith relevant quotas. For example -
 1. dynamic language translation offered by apis.smartclean.translate
 2. real-time TSDB queries through a rich query language offered by apis.smartclean.tsdbmemory
 3. real-time websocket based publish/subscribe APIs by apis.smartclean.rtdatagateway
 
Reach out to your account executive to enable these APIs and obtain an API key.

Enhancement
{: .label .label-green }

**Emit (Device) Slot Events**

1. Automatically perform pre-defined actions when any certain condition becomes true with any Device Slot.
2. Desired conditions are captured and generated as events by the application running for the Device Slot.
3. Example pre-defined _logical action_: send request to a service or notification to a workforce member.
4. Example pre-defined _physical action_: Turn on / Turn off your device. 
    This requires you to connect your device using our IoT Switch. 
    Example use case: Bad air quality event from the slot: Air Quality monitoring is configured to turn on a fan.


Enhancement
{: .label .label-green }

**Email notification for completed web reports.**

An email notification with relevant details is sent to pre-configured recipients when any requested web report 
becomes ready for viewing.

Pre-release
{: .label .label-purple }

- Matrix IAM will now allow you to define boundary permissions for your application. This is especially helpful in cases where you want your users to be limited by an upper bound while still giving them the flexibility to choose/edit their roles.

- Matrix IAM will allow you to configure your Single Sign On providers as a means to allow your existing users to access Matrix.
