---
layout: default
title: SSO using Microsoft Azure Active Directory
parent: Single Sign On
grand_parent: Identity and Access Management (IAM)
has_children: false
has_toc: false
nav_order: 1
---

# Single Sign On with Microsoft account 
IAM Provider: [Microsoft Azure (Active Directory)](https://azure.microsoft.com/en-us/services/active-directory).

## Overview
1. Use case - You want to use your Microsoft organization email to access our platform. 
2. **Pre-requisites:**
   1. Register your enterprise application to use a web application for authentication.
      1. Required to allow Azure AD to request our authorization endpoint for giving access to our platform.
      2. See point 3 in the "Steps involved" section below.
   2. Register your application in our platform.
      1. For identifying your Microsoft Azure enterprise application.
      2. See point 5 in the "Steps involved" section below.
      
For further details on this process visit the page for
[OIDC Protocol in Microsoft Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-protocols-oidc)


## Steps involved:
1. Create an enterprise application in Microsoft Azure AD.
   1. [Step by step guide](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)
   2. [Example of this process](https://docs.microsoft.com/en-us/power-apps/developer/data-platform/walkthrough-register-app-azure-active-directory)
   3. Find this listed in Enterprise Applications (under the "Manage" section) and click on it.
   4. Click on Authentication (under "Manage") to view relevant details and do the below steps.

2. Create a Secret Key for this application and copy it somewhere safe.
   1. Do this by clicking the link next to Client credentials.

3. Allow your enterprise application to redirect to our web application for authentication.
   1. Do this by clicking the link next to "Redirect URIs
   2. Then add our authorization endpoint here:
   3. `https://matrixsso.smartclean.io/oauth2/idpresponse`
   4. This fulfils the first pre-requisite (1/2)

4. Click the Endpoints tab and copy the URL of "the OpenID Connect (OIDC) metadata document" somewhere safe.

5. Provide your SmartClean account representative this Application Secret and OIDC URL
   1. This allows us to register your Microsoft Azure enterprise application.
   2. Fulfils the second pre-requisite (2/2)

6. Your HR team or your IT admin can now allocate appropriate users in your directory to access the 
application through their registered email addresses in your domain.

7. Our platform will request the following scopes when authentication is required:
   1. _Open ID_ 
   2. _user.read_

8. Refer to example screenshots from this process in the "Screenshots" section below. 
   1. The _enterprise application_ is called: **Matrix SmartClean CSM Team** 
   2. The application is created by the _organization_ **SMARTCLEAN TECHNOLOGIES PTE LTD**

## Notes
**Known issue** with Azure AD version 1 and version 2 in Manifest of your enterprise application:
1. The Manifest file may show null or "1" as the value for the key "accessTokenAcceptedVersion"
2. Refer to corresponding screenshot in the Screenshots section below. 

This requires the OIDC discovery URL to be `https://sts.windows.net/<tenant id>` or `https://sts.windows.net/<tenant id>/v2.0`
since the issuer (iss) is different.

**Resolution:**
- To allow the issuer to be properly set based on the endpoints shown in your application, please update the Manifest
  (to highlight the version as 2).
- In this case, Matrix will use the OIDC discovery URL as `https://login.microsoftonline.com/<tenant id>/v2.0` for IAM federation.


## Screenshots

### Microsoft Azure AD - Homepage
<img alt="Microsoft Azure AD Home" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-home.png" width="800"/>

### Microsoft Azure AD - Enterprise Application: Overview
<img alt="Microsoft Azure AD Application Details" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-appdetails.png" width="800"/>

### Microsoft Azure AD - Enterprise Application: Endpoints
<img alt="Microsoft Azure AD Application Endpoints" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-details.png" width="800"/>

### Microsoft Azure AD - Enterprise Application: Manifest
<img alt="Resolution - App Manifest" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-manifest.png" width=800/>
