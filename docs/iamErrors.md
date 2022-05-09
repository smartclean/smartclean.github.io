---
layout: default
title: Errors
parent: Identity and Access Management (IAM)
has_children: false
has_toc: false
nav_order: 2
---

# Error Codes and Responses from IAM

This section highlights the error codes returned by the IAM module alongwith a 403 status code.

An example response could like the following:

```json
{
        "code": "IMPLICIT_DENY",
        "message": "The module and operation you are trying to access was not allowed explcitily by the role you have."
}
```

## Error codes and their details
### IMPLICIT_DENY

> The module and operation you are trying to access was not allowed explcitily by the role you have.

This error code implies that the role's policy set did not explicitly allow the operation being performed, hence resulting in this final decision.

To resolve this, you can add wildcard prefix or allow the operation explicitly in one of the policy statements.

### EXPLICIT_DENY

> The module and operation you are trying to access is not allowed by the role you have.

This error code implies that a policy attached to the role assumed explicitly denied the operation being performed.

### TRUST_RELATIONSHIP_VIOLATION_EXPLICIT_DENY

> Your request to assume the role allocated was explicitly denied by the trust relationship.

A trust relationship explicit denial is enforced when the identity trying to assume the role was explicitly marked by the role creator to be denied.

### TRUST_RELATIONSHIP_VIOLATION_IMPLICIT_DENY

> Your request to assume the role allocated was implicitly denied as the trust relationship did not explicitly allowed this.

A trust relationship implicit denial is enforced when no principal clause explicitly matched the SRN (SmartClean Resource Name) of the identity.

For a trust relationship to be successfully assumed by the principal/identity in the context of the property, it must be explicitly allowed in the principal clause of the policy.
