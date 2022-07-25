---
layout: default
title: 2022-07-23
parent: Release Notes
has_children: false
has_toc: false
nav_order: 17
---

# Release notes for 2022-07-23


## Pre-Releases:

Pre-release
{: .label .label-purple }

A new application that handles the following use cases is in the pre-release testing pipeline:
1. Air quality monitoring solution
2. Occupancy monitoring solution


Pre-release
{: .label .label-purple }

**Add-on features as a service:**
- A service that aggregates add-on functions to enhance the capability of Matrix is being tested internally. 
- These add-on functions may be developed in-house or provided by our technology partners.
- A section dedicated to this service for add-on functions will be added to the online documentation on release. 
- Examples of such add-on functions are:
  - Translation: Translate content from Matrix to your desired language
  - Realtime data gateway: For access to realtime data from certain data sources in Matrix.


## New features:

Feature
{: .label .label-blue }

Matrix panel application for display tablets:

1. The Matrix panel application is now stable and will be available to install from Android play store and iOS app store. 
2. This app allows users in your property to use this as single point of interaction on a tablet machine.
3. This is helpful in cases where people from your workforce do not have smartphones. 
4. Details about this application will be updated in the online documentation here.


## Enhancements:

Enhancement
{: .label .label-green }

Python SDK - Last task completed for a Zone

1. New utility introduced in our PythonSDK for Workforce Management API to get relevant information about Tasks. 
2. The utility is categorised into the following classes:
   1. Task - functions to extract relevant information from any workforce Task (obtained from Workforce Management API)
   2. Last task completed - function to get the latest Task completed for a Zone, and get the time of completion.
