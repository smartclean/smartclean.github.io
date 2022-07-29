---
layout: default
title: Single Sign On
parent: Identity and Access Management (IAM)
has_children: true
has_toc: true
nav_order: 3
---

# Single Sign On
- Single Sign-On (SSO) for applications with supported identity providers.

## Overview
1. This is applicable only if you are using services by any of the standard enterprise IAM providers listed below.
2. Identity providers currently supported for SSO access to our platform:
   1. [SSO with Microsoft account (Azure Active Directory)](/iam_sso_ms.html)
3. This integration allows access to our platform with the same credentials used to access your enterprise software. 
4. **Pre-requisite:** You need to register your identity (as an application) and the corresponding identity provider in our platform.

## Benefits:
1. No need to register for a SmartClean account to access our services.
2. Your Property Administrators can invite users to your property using their email id registered with the IAM provider

## Steps involved:
1. Contact your SmartClean account representative to initiate the SSO integration setup.
2. Create an [OpenID Connect (OIDC)](https://openid.net/connect) application with supported IAM provider and give us:
   1. _Application ID_ and corresponding _Secret Key_
   2. _Discovery URL_
3. We will whitelist the Discovery URL (domain of this IAM provider) to allow sign-in to our platform.
4. Matrix will integrate with your IAM and request the following scopes when authentication required:
   1. Open ID 
   2. Email ID

## Outcome:
After the setup process is completed: 
1. Please choose your IAM provider when signing in to our platform.
2. You will then be redirected to sign in with the IAM provider.

## Authorization mechanism used:
1. This process is based on an [industry standard authorization mechanism: OAuth2](https://oauth.net/2)
2. Specific type: [Authorization Code grant with PKCE extension](https://oauth.net/2/grant-types/authorization-code).

## Process flow:
The diagram below shows the typical process flow from a user's perspective.

<img alt="IAM SSO" src="https://www.smartclean.io/matrix/assets/common/images/IAM/SSO-OIDC-Matrix.png"/>


Note:
This process is also involved in one of the 
[standard options we provide for integration with external systems](https://www.docs.smartclean.io/integrations.html):

Introduced in the page: [Integration based on identity federation](https://www.docs.smartclean.io/integrations_sso.html)
