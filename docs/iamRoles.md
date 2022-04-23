---
layout: default
title: Roles
parent: Identity and Access Management (IAM)
has_children: false
has_toc: false
nav_order: 1
---

# What are roles ?
A role is a collection of do's and dont's stated explicitly to a principal performing operations within your entity, org, property or self.

Each principal can assume one role while performing any operation in Matrix.
The sections below describe some common terminologies found in the IAM dashboard and their implications alongwith associated example usecases.

<img alt="Role Example" src="https://www.smartclean.io/matrix/images/roleExample1.png" style="width: 30%" />

# Terms used
1. Entity - An entity is an umbrella term used to refer generally to a property or an organisation.
The segregation allows for easy segregation of APIs and micro-services in general and hence their various usecases offered by SmartClean Matrix modules or technology partner solutions.

2. Principal - A principal refers to any accessor of system and services within an entity such as dashboard users and API users.
Each principal can access resources within an entity by using the following mechanisms.

## Authorization mechanisms

a. Basic authorization: Basic user identities comprise of a username and password that are sent within the *Authorization* header of each request.

b. HMAC authorization: [Hash-Based Message Authentication Code](https://datatracker.ietf.org/doc/html/rfc2104) (HMAC) is a secure method for securing access to an entity.
SmartClean's HMAC based implementation details are described here.

c. OAUTH2.0 authorization: [OAUTH](https://datatracker.ietf.org/doc/html/rfc6749) is the primary means of authorization for user facing applications using the **Authorization Code Grant** accessed usually over a web or a mobile user interface or third party solutions offered by technology partners using the **Client Credentials Grant**.

d. SSO authorization: Single Sign On authorization covers the use of other methods through federation such as SAML, Active Directory or custom SSO implementations by third party providers.

# How does a principal get a role in my entity (property/organisation) ?
Matrix requires each principal to have a valid role while performing any operation.
The role is provided to the principal depending on their access type as follows:

1. **Principals using basic authorization schemes**: Each basic user must be allocated a system or custom defined role alongwith a correct trust relationship that allows this user to assume this role in the context of your entity.

2. **Principals using HMAC authorization schemes**: Each HMAC access key must be allocated a system or custom defined role alongwith a correct trust relationship that allows this access key to assume this role in the context of your entity.

3. **Principals using OAUTH scheme**: Users accessing the standard web or mobile applications in Matrix must belong to a valid seat within the entity which is allocated to a **UserGroup**.

Each usergroup is finally allocated a role which is then assumed by these principals.

# User Groups
User groups allow grouping of various seats in an entity by their access patterns or *persona* colloquially.

Each user group is assigned a role that governs what can users access. A user group also controls which applications can the principal access.

This scope can be further reduced through means of ABAC on contextual information presented to the IAM evaluation engine.

# Trust Relationship
A trust relationship is a specification of the following key processes evaluated prior to allowing a princial to assume the role successfully.

Prior to performing the operation to validate a trust relationship, the following contextual information

1. What is the access mechanism used by the principal.

2. What are the attributes of the principal - such as IP, identity, geolocation.

# Policy Set
Each role contains one or more policy sets that define access rules as an array of *statements*.

Note that Matrix relies on deny first approach, therefore, any statement found to be denying an operation explicitly in the policy set will be denied immediately and evaluation terminated.

# System defined and custom roles
Matrix offers many system defined roles that can be used to implement various common usecases for access requirements.

Each system defined role has a status -

1. **ACTIVE** - The role is active and can be used.

2. **DEPRECATED** - The role has been marked as inactive and cannot be used.

3. **PENDING_DEPRECATION** - The role will be marked as inactive within 90 days and should not be used.

Some examples of commonly used roles in system are -

1. **SMARTCLEAN#PropertyAdmins**: Allows complete administrative access to all functions within a property.

2. **SMARTCLEAN#QRFeedbackUsers**: Allows general users to provide feedbacks or report defects in a property through QR codes.

3. **SMARTCLEAN#IAMViewOnly**: Provides view only access to the IAM module of the property.

4. **SMARTCLEAN#HOUSEKEEPING**: Provides access to the *Housekeeping* mobile application and all its functions.

5. **SMARTCLEAN#FM**: Provides access to the *FM* mobile application and all its functions.
