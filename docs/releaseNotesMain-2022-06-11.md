---
layout: default
title: 2022-06-11
parent: Release Notes
has_children: false
has_toc: false
nav_order: 14
---

# Release notes for 2022-05-28

Enhancement
{: .label .label-green }
PythonSDK - Sync client returns the original response object of the HTTP request instead of the JSON data extracted from the response body.
This allows clients to extract any desired attributes from the response instead of being restricted to the response body,
This is also helpful in case the response body is empty.
