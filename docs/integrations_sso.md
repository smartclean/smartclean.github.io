---
layout: default
title: Integration based on single sign on
parent: Integrations
has_children: false
has_toc: false
grand_parent: SmartClean Matrix
nav_order: 5
---

# Integration based on single sign on
Use this option for accessing our services by logging in with a supported identity provider.

**Pre-requisite:**
- You should have an account with a federated identity provider
- Any interface that allows you to login to this identity provider and make requests to our services.

**Outcome:**
- You should be able to make web https requests to our services without the need for obtaining credentials from us.

**Our Solution:**
Matrix federated login

#### Matrix federated login
**Use it for:** Making web (https) requests to our platform without the need for SmartClean login. 
[comment]: <> (2. **Introduced in our documentation at:** [Matrix federated login]&#40;&#41;)

**Steps to access our services by federated login:**
1. Register your application with us (you will be provided an _Application ID_)
2. Obtain authentication token issued by your identity provider.
3. Ensure this token is set as value of request header: "Authorization" for all requests made to Matrix.
4. Paste the _Application ID_ as value of request header: "x-sc-auth" for all requests made to Matrix

**Supported identity providers:**
1. Microsoft Azure
