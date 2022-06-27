---
layout: default
title: 2022-06-25
parent: Release Notes
has_children: false
has_toc: false
nav_order: 15
---

# Release notes for 2022-06-25

## Features:

Feature
{: .label .label-blue }

Grids: Improved flow for floor creation in bulk and continuations.


Feature
{: .label .label-blue }

Grids: Added a column indicating whether the operating hours for the zones are custom or same as building.


Feature
{: .label .label-blue }

Workorders: Edit shift allows you to now perform operations more seamlessly than before. 
Earlier, editing task timings, details, deletions were not easy to use.


Feature
{: .label .label-blue }

IAM v1.3a now allows you to invoke Matrix APIs in context of a property by registration of your application. 

If you are already using Oauth authorization code grant and wish to seamlessly integrate Matrix calls with the same, 
application registration can allow property owners to provide this access to your application in their properties.

Additionally, you can register a new standard Oauth application with client credentials grant.


## Enhancements:

Enhancement
{: .label .label-green }

Audits tally/performance report now includes additional methods to allow categorisation followed by performance score evaluation. 

This is inline with the development towards a full-fledged performance report generation module in Matrix.


## Pre-Releases:

Pre-release
{: .label .label-purple }

Python and Java SDKs will allow users to invoke functions based on a federated token.
