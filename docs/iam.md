---
layout: default
title: Identity and Access Management (IAM)
has_children: true
has_toc: true
nav_order: 2
---

# IAM
Latest Stable Version:
v1.1
{: .label .label-green }

Identity and Access Management (IAM) is one of the primary building blocks of Matrix.

Matrix IAM is inspired from the principles of [XACML](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=xacml).

As a result, the concepts of Policy Enforcement Point (PEP), Policy Decision Point (PDP), Role, Policy/PolicySet, and others will be used to document their usecases and meanings.

Furthermore, by adding an [AWS IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html) equivalent of trust relationship per role, Matrix is able to achieve various usecases that are commonly found for API based integrations including the third party application development frameworks provided by SmartClean.

> Matrix IAM operates on a **Deny-Overrides** mechanism, that is, if any explicit denial is encountered while evaluating the policies, the evaluation will stop and the request is denied.

In certain exceptional cases, this denial can still be rendered **indeterminate** if *conditions* were used in the evaluation of the matching statement of the permissions policy applicable.

If no policy results in an explict allowance of the operation, the indeterminate outcome results in a final PEP decision of implicit **Deny**.

> Note that each identity can assume a single role while performing an API operation.

Matrix allows three primary means of invoking the APIs -

- **Basic authorization**: This scheme allows quick testing of certain APIs in the property. Use of basic authorization in production applications is not preferred, when the applications can use HMAC signatures.

Basic authorization keys are assigned a role directly by adminstrators from the IAM module.

- **HMAC authorization**: [HMAC](https://www.rfc-editor.org/info/rfc2104) authorization is used by default in the SDKs and is the preferred means of API calls for production use.

HMAC authorization keys are assigned a role directly by adminstrators from the IAM module.

- **JWT authorization**: This mechanism is used primarily by the mobile and web applications to perform operations within a property.

Dashboard or mobile users assume the role specified in the user group which they belong to as a part of the property.

# Request Authorization Steps
The overall lifecycle of any incoming API call through the IAM is depicted in the diagram below.

![IAM Flow](https://www.smartclean.io/matrix/images/iam/IAM-Flow-V1.jpeg)

A brief description of the above process flow is as follows.

1. Each API call enters the IAM alongwith its contextual data such as the caller's IP, entity (property) being accessed, caller's identity and the operation being performed.

2. The IAM module will try to find a session for this identity in the context of the property.
If a session could not be found, the system will try to create the session by assuming the role specified for the identity.
If the role assumption fails due to any error conditon (see [Errors](/iamErrors.html)), the operation is denied.

3. If the session was found, the PEP (policy enforcement point) cache decision is checked for existence.
If this decision is found, the final result is returned to the caller, else the PEP makes a request to the PDP (policy decision point) to evaluate the policy set allocated to the role.

4. Post policy set evaluations, the PEP generates a final result of **Allow** or **Deny** depending on the outcomes.
