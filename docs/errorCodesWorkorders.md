---
layout: default
title: Error Codes
parent: Workorders
has_children: false
has_toc: false
nav_order: 100
---

# Error Codes
Following error codes exist in the *workorders* module with their description. 

| Error Code      | Description |
| LIMIT_VIOLATED | In the cases when limits get breached for the addition of any entity. For example, The maximum number of tasks any task group can be allocated is 20. For more information on corresponding limits refer https://www.docs.smartclean.io/limitsQuotasWorkorders.html| 
| MISSING_PARAMETERS | When mandatory parameters are missing for a particular operation to take place. |
| QUERY_LENGTH_EXCEEDED | Can't query more than the limit defined in one go. | 
| WRONG_PARAMETERS | For certain operations only defined values can be provided. If instead of those defined values something else is provided will lead to this error. |
| failure | Generic error code in the cases when due to some circumstances an error has occurred. |