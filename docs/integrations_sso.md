---
layout: default
title: Integration based on identity federation
parent: Integrations
has_children: false
has_toc: false
nav_order: 5
---

# Integration based on identity federation
Use this option for accessing our services by using a registered [OAuth](https://oauth.net/2) application

**Pre-requisite:**
- You must have registered your application in your identity provider with optional application secret.
- You have an application ID (client_id) from above step and URL to [JWK (JSON Web Key) set](https://auth0.com/docs/secure/tokens/json-web-tokens/json-web-key-sets).
- Any interface that allows you to login to this identity provider through any of the supported
OAuth grants and returns you an access token or identity token.

**Outcome:**
- Once the property admin has enabled your application in their property and assigned a role, your application
should be able to make relevant requests to Matrix in that property using the tokens received above.

**Our Solution:**
Matrix federated login

#### Matrix federated login
**Use it for:**
- Making API calls to our platform without the need for SmartClean login mechanisms such as generation of basic or HMAC credentials per property.
- Integrate Matrix data points and analytics in your existing platform.
- Develop a new application for Matrix ecosystem.

**Steps to access our services by federated login:**
1. Register your application with us 
   - Please provide us your client identifier and URL to the JWK set. 
   - We will provide you a QUID (Qualified UID) as the unique application registration identifier in Matrix, please keep it safe.
2. Obtain authentication token issued by your identity provider.
3. Ensure this token is set as value of request header: "Authorization" for all requests made to Matrix.
4. Paste the QUID as value of request header: "x-sc-auth" for all requests made to Matrix

**Supported identity providers:**

1. [Microsoft Azure AD](https://azure.microsoft.com/en-us/services/active-directory)
   - Please use the identity token obtained as value of the header "Authorization" in all web https requests to Matrix  
2. [Amazon Cognito](https://aws.amazon.com/cognito)
   - Please use the access token obtained as value of the header "Authorization" in all web https requests to Matrix
3. [Auth0](https://auth0.com)
   - Please use the identity token obtained as value of the header "Authorization" in all web https requests to Matrix 
4. [Firebase Auth](https://firebase.google.com/docs/auth)
   - Please use the identity token obtained as value of the header "Authorization" in all web https requests to Matrix
