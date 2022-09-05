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
IAM Provider: [Microsoft Azure - Active Directory (AD)](https://azure.microsoft.com/en-us/services/active-directory).

## Overview

1. Use case - You want to use your Microsoft Azure / organization email to access our platform. 

2. **Pre-requisites:**
   1. Configure your Azure AD enterprise application to request our authorization service for authentication.
      1. See point #2.3. in the "Steps involved" section below.
   2. Register this application in our platform.
      1. For identifying your Microsoft Azure enterprise application.
      2. See point #4. in the "Steps involved" section below.
      
For further details on this process visit the page for
[OIDC Protocol in Microsoft Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-protocols-oidc)


## Steps involved:

1. Create an enterprise application in Microsoft Azure AD.
   1. [Step by step guide](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)
   2. [Example of this process](https://docs.microsoft.com/en-us/power-apps/developer/data-platform/walkthrough-register-app-azure-active-directory)
   3. After creation, you can see this listed in Azure AD homepage, option: _Enterprise Applications_ (under "Manage").
   4. For example: refer to screenshot #2, in the _Screenshots_ section below.

2. Configure authentication for this application in Microsoft Azure AD
   
   1. Click on Authentication (under "Manage") and do **below three steps**.
      1. For example: refer to screenshot #2, in the _Screenshots_ section below.
   
   2. Create a Secret Key for this application and copy it somewhere safe.
      1. Do this by clicking the link next to _Client credentials_.
      2. Required for step 6, below.
      
   3. Redirect your application to our authorization endpoint for authentication.
      1. Do this by clicking the link next to "Redirect URIs
      2. Then add our authorization endpoint (URL below):
      3. `https://matrixsso.smartclean.io/oauth2/idpresponse`
      4. This fulfils the first pre-requisite (1/2)

   4. Click the Endpoints tab and copy the URL of "the OpenID Connect metadata document" (OIDC config URL) somewhere safe.
      1. Required for the next step.
      2. Refer to Screenshot #3, below.

3. Provide your SmartClean account representative this _Application Secret_ and _OIDC config URL_
   1. This allows us to register your Microsoft Azure AD enterprise application.
   2. Fulfils the second pre-requisite (2/2)

4. Our platform will request the following scopes when authentication is required:
   1. _Open ID_ 
   2. _user.read_

## Outcome:
Your HR team or your IT admin can now allocate appropriate users in your directory to access the 
application through their registered email addresses in your domain.
   
## Notes
**Known issue** with Azure AD version 1 and version 2 in Manifest of your enterprise application:
1. The Manifest file may show null or "1" as the value for the key "accessTokenAcceptedVersion"
2. For example: refer to screenshot #4, in the _Screenshots_ section below. 

This requires the OIDC discovery URL to be `https://sts.windows.net/<tenant id>` or `https://sts.windows.net/<tenant id>/v2.0`
since the issuer (iss) is different.

**Resolution:**
- To allow the issuer to be properly set based on the endpoints shown in your application, please update the Manifest
  (to highlight the version as 2).
- In this case, Matrix will use the OIDC discovery URL as `https://login.microsoftonline.com/<tenant id>/v2.0` for IAM federation.


## Screenshots
Below are some screenshots for an example Enterprise Application in Azure AD.
1. The _enterprise application_ is called: **Matrix SmartClean CSM Team** 
2. This is created by the _organization_ **SMARTCLEAN TECHNOLOGIES PTE LTD**

### 1. Microsoft Azure AD - Homepage
<img alt="Microsoft Azure AD Home" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-home.png" width="800"/>

---
### 2. Microsoft Azure AD - Enterprise Application: Overview
<img alt="Microsoft Azure AD Application Details" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-appdetails.png" width="800"/>

---
### 3. Microsoft Azure AD - Enterprise Application: Endpoints
<img alt="Microsoft Azure AD Application Endpoints" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-details.png" width="800"/>

---

### 4. Microsoft Azure AD - Enterprise Application: Manifest
<img alt="Resolution - App Manifest" src="https://www.smartclean.io/matrix/assets/common/images/IAM/OIDC-365-manifest.png" width=800/>
