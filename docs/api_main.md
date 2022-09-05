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

## Documentation
For details about these requests and examples, refer to the documentation at:

[https://documenter.getpostman.com/view/2593073/UVsPQ4vL](https://documenter.getpostman.com/view/2593073/UVsPQ4vL)

## Postman collection
These requests have been put in a Postman collection.

**Import link:** `https://www.getpostman.com/collections/53dff3af449ea3b1d7c6`

1. Postman is a tool for using and sharing details about web requests. 
   - Read more about it here: [https://www.postman.com](https://www.postman.com).
2. There are two ways to use Postman:
   1. Web console - a Postman account is required to sign in and use the console.
   2. Desktop app - can be used without signing in.

**Important:**
 - The import link is meant to be used by the Postman application.
   - So, there is no use of opening this link using your browser. 
 - Ensure you have received from us, authentication credentials, specifically for using this postman collection. 
   - If you don't have it, please request these from our account manager.
   - Without this the requests will not work
 - Please copy or note down this link, as you need to use it in "_Step 4_" of "_How to use these requests_" below.

### How to use these requests in Postman

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


## Authentication:

Matrix requests are for authorised users only. Every request must be provided with authentication credentials to succeed.

You can use the following type of credentials to authenticate your requests:
1. Basic keys (A pair of username and password)
2. Custom HMAC keys (A pair of access Key and secret key)
3. Custom identity provider
4. The diagram below illustrates this.

<img alt="Ways to authenticate requests to Matrix" src="https://www.smartclean.io/matrix/images/IAM-App-Federation.jpeg" width="800"/>

**More information:**
1. Authentication is necessary for all requests, without which the request will fail.
2. If any request indicates Unauthorised or TOKEN_INVALID in the response it means the credentials are not specified, or expired.
3. This postman collection enforces the "Basic" authentication scheme. 
- Learn more about authentication schemes here: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication)
4. You need to paste the credentials given to you in the "Variables" section of this collection.
- This is to be done only once after the Collection is imported in Postman.
5. Please obtain your credentials (Username and Password) from our representative, then follow up from the below 
section: "Set your username and password in the Postman collection")
6. If desired, you may switch to a more secure authentication (based on SHA-256 HMAC signing)
   1. You will be provided the credentials: Access Key and Secret Key (Used instead of username and password)
   2. See the section: "Switch to HMAC Signing for more secure Authorization" below.

### Set your username and password in the Postman collection:
1. Go to the tab "Variables" for this collection. 
- Tip: In Postman, click on this Collection in your sidebar, then click on the "Variables"
2. Paste the Username and Password provided to you as the CURRENT VALUE of the variables: "sc-username" and "sc-password" respectively.
- Important: Paste these values under the column: "CURRENT VALUE" for the corresponding "VARIABLE" name (there is no need to change the values under the column: "INITIAL VALUE", as these are just dummy placeholders)
3. Press CTRL + S or click the save icon on top right to save the changes.

### Switch to HMAC Signing for more secure Authorization
In case you want to switch from the simple (Basic) authentication to the more strict HMAC based authentication, please do the following.

1. Request our representative to receive your HMAC credentials (i.e. Access Key and Secret Key).
2. Go to the Variables section in the collection and Update the CURRENT VALUE of the variable: "*auth-type*" to **hmac** (from the default basic)
3. Paste the Access Key and Secret Key given to you as the CURRENT VALUE of the variables: "*sc-hmac-access-key*" and "*sc-hmac-secret-key*" respectively.
