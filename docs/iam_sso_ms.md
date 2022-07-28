---
layout: default
title: SSO with Microsoft account
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
   1. Register an application as a Microsoft account in our platform.
   2. Add the following web endpoint to Azure AD.
      1. Required to allow Azure AD to request our authorization endpoint for giving access to our platform. 
      2. This URL is used to authorize your Microsoft account and obtain the corresponding access token.

For further details on this process visit the page for
[OIDC Protocol in Microsoft Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-protocols-oidc)


## Steps involved:
1. Create an enterprise application in Microsoft Azure AD.
   1. [Step by step guide](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)
   2. [Example of this process](https://docs.microsoft.com/en-us/power-apps/developer/data-platform/walkthrough-register-app-azure-active-directory)

2. Create Secret Key for this application and copy it somewhere safe.

3. Register a web application (Under Authentication section of this application)
   1. For redirect URIs, add this endpoint (our authorization endpoint):
   2. `https://auth.smartclean.io/oauth2/idpresponse`

4. Click the Endpoints button and copy the URL of "the OpenID Connect (OIDC) metadata document" somewhere safe.

5. Provide your SmartClean account representative this Application Secret and OIDC URL.

6. Your HR team or your IT admin can now allocate appropriate users in your directory to access the application through their registered email addresses in your domain.

**Note:** 
1. "Screenshots" section below has some screenshots from this process.
2. In these screenshots, the _enterprise application_ is called: **Matrix SmartClean CSM Team** created by the
 _organization_ **SMARTCLEAN TECHNOLOGIES PTE LTD**

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
