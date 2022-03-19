---
layout: default
title: API
has_children: true
has_toc: true
nav_order: 10
---

# Matrix Web Services
_Relevant requests from our web services are also accessible to authorised users._

**Services included:**
1. Grids
2. Device management
3. Work orders
4. Metrics

Note:
URL of each request starts with the following (base-url):
*https://console.smartclean.io/prod/v2*

## Documentation
For more details, view the [Documentation](https://documenter.getpostman.com/view/2593073/UVktqZWQ)

## Postman collection
These requests have been put in a [Postman](https://www.postman.com) collection.

To access these, please import the below link using Postman.
- [Matrix postman collection](https://www.getpostman.com/collections/a41502dfa9b37c964177)

Note:
There are two ways to use Postman:
1. Web console - a Postman account is required to sign in and use the console.
2. Desktop app - can be used without signing in.

## How to access these requests:

You will need to open Postman (desktop client or web console) and sign in to your Postman account first.

1. Click on "Collections" on the left vertical navigation bar.
   1. If you don't see this, you will have to open a "Workspace" first (or create one if none are there)
2. Click on "Import" then Click on the tab "Link" on the box that opens. 
3. Paste the link to Postman collection in the box under "Enter a URL" and press Continue
   [link to Postman collection](https://www.getpostman.com/collections/a41502dfa9b37c964177)
4. A confirmation dialog appears, please click on Import
   Note: In case you already imported this before, it will ask you to "Replace" or "Import as Copy"
5. Click on the newly imported collection: Matrix
6. Click on "Authorization" if not already selected (next to Tests)
   1. If this is already selected, you will see input box for Username and Password and "Basic Auth" next to Type
7. Enter the Username and Password provided to you in these input boxes.
8. Depending on the request, please provide desired data in the "Params" (Query Parameters) or Body
   1. Refer to the documentation for the request on what data needs to be given
   2. If data is required in the body, it will be mentioned, otherwise provide data in the "Params"
9. Click "Send" on the request. The response will indicate whether the request succeeded or failed, along with a reason for failure.
