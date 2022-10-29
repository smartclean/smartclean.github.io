---
layout: default
title: 2022-06-11
parent: Releases in 2022
grand_parent: Release Notes
has_children: false
has_toc: false
nav_order: 14
---

# Release notes for 2022-06-11

## Features:

Feature
{: .label .label-blue }

Java SDK version 1.1 has been released in beta here: 

https://github.com/smartclean/smartclean-sdk-java-builds

The above allows interactions with Matrix functions and returns a JSON output result.
Breaking changes should be expected for types returned once the SDK is released generally.


Feature
{: .label .label-blue }

Workorders web dashboard has major changes in Task Board presentation layer.


Feature
{: .label .label-blue }

Task groups can now be associated to multiple zone categories (up to 5) or all zone categories as a special case.

This allows you to reuse task groups across multiple zone types instead of re-defining them again (earlier flow).


Feature
{: .label .label-blue }

Tasks inside task groups can now be dragged to re-order them in sequence desired.


Feature
{: .label .label-blue }

Shift creation process has been enhanced to show dropdowns for easy selection of shift times.

You can seamlessly create shifts that span beyond 0000 hours of a day.


Feature
{: .label .label-blue }

Reporting of incident in workorders dashboard now allows you to upload image attachments too.


Feature
{: .label .label-blue }

Grids module features enhancements to selection of coordinates during building creation or edit.


Feature
{: .label .label-blue }

Operating hours in Grids web dashboard for building and zones has been enhanced to allow better user interaction and usability.


## Enhancements:

Enhancement
{: .label .label-green }

Reports module now performs a pre-condition check prior to report generation job submission: 
It checks whether the project has any valid data points that will show in the report or not.


Enhancement
{: .label .label-green }

PythonSDK - Sync client returns the original response object of the HTTP request instead of the JSON data extracted
from the response body.
Note: The Sync client makes all requests sequentially (instead of asynchronously, which the Async client does)

This allows clients to extract any desired attributes from the response instead of being restricted to the response 
body. This is also helpful in case the response body is empty.
