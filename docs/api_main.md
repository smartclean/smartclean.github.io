---
layout: default
title: API
has_children: false
has_toc: false
nav_order: 10
---

# Matrix Web Services
_Relevant requests from our web services are also accessible to authorised users._

**Services included:**
1. Grids
2. Device management
3. Metrics
4. Work orders

Note:
> Each request must start with the following URL:
>
> *https://console.smartclean.io/prod/v2*

## Postman collection
These requests have been put in a Postman collection.

1. Postman is a tool for using and sharing details about web requests. 
   - Read more about it here: [https://www.postman.com](https://www.postman.com).
2. There are two ways to use Postman:
   1. Web console - a Postman account is required to sign in and use the console.
   2. Desktop app - can be used without signing in.

### Documentation
For details about these requests and examples, refer to the documentation at the link:

_https://documenter.getpostman.com/view/2593073/UVsPQ4vL_

### How to use these requests

Ensure you have received from us, a Username and Password, specifically for using this postman collection.
   If you don't have it, please request these from our account manager.

Import the below link using Postman.

_https://www.getpostman.com/collections/f3bbb37cf3dbec166bb1_

**Detailed Steps:**
1. Open the Postman application
2. Click on "Collections" on the left vertical navigation bar.
   1. If you don't see this, you will have to open a "Workspace" first (or create one if none are there)
3. Click on "Import" then Click on the tab "Link" on the box that opens. 
4. Copy and Paste the above to link to Postman collection in the box under "Enter a URL" and press Continue
5. A confirmation dialog appears, please click on Import 
   1. In case you already imported this before, it will ask you to "Replace" or "Import as Copy"
   2. You should now see a new collection on the left sidebar called "Matrix Services".
6. Click on the collection: "Matrix Services"
7. Enter the Username and Password in the "Variables" section.
   1. Click on the "Variables" tab 
   2. Enter the Username given to you under the column: CURRENT VALUE for the VARIABLE: "_sc-username_"  
   3. Enter the Password given to you under the column: CURRENT VALUE for the VARIABLE: "_sc-password_",
   4. Click on the Save icon on the top right.
8. Depending on the request, please provide desired data in the "Params" (Query Parameters) or Body
   1. Refer to the documentation for the request on what data needs to be given
   2. If data is required in the body, it will be mentioned, otherwise provide data in the "Params" section.
9. Click "Send" on the request. The response will indicate whether the request succeeded or failed, 
along with a reason for failure.


### Authentication:
Authentication is necessary for all requests, without which the request will fail.

By default, this collection enforces the "Basic" authentication scheme. 
- Learn more about authentication schemes [here:](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication).

For the default authentication, your Username and Password is sufficient
- See the "Detailed Steps", under the "How to use these requests" section above. 

For more details, and how to configure this, please read the Authentication section of the 
document whose link is given in the "Documentation" section above
