---
title: "Update governanceRoleAssignmentRequests"
description: "Enable administrators to update their decisions (`AdminApproved` or `AdminDenied`) on governanceRoleAssignmentRequests that are in status of `PendingAdminDecision`."
localization_priority: Normal
doc_type: apiPageType
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
---

# Update governanceRoleAssignmentRequests

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Enable administrators to update their decisions (`AdminApproved` or `AdminDenied`) on [governanceRoleAssignmentRequests](../resources/governanceroleassignmentrequest.md) that are in status of `PendingAdminDecision`.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

>**Note:** In addition to the permission, this example requires that the requester have at least one Active Global Administrator or Privileged Role Administrator assignment. 

|Permission type      | Permissions              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | PrivilegedAccess.ReadWrite.AzureAD  |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | PrivilegedAccess.Read.AzureAD |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /privilegedAccess/aadRoles/roleAssignmentRequests/{id}/updateRequest   
```

## Request headers
| Name           | Description|
|:---------------|:----------|
| Authorization  | Bearer {code}|
| Content-type  | application/json|

## Request body

|Parameters	     |Type	                 |Required |Description|
|:-------------|:----------------------|:--------|:----------|
|reason        |String                 |✓        |The reason provided by the administrator for his decision.|
|decision        |String                 |✓        |The administrator decision of the role assignment request. The value should be updated as `AdminApproved` or `AdminDenied`.|
|schedule      |[governanceSchedule](../resources/governanceschedule.md)|        | The schedule of the role assignment request. For status of `AdminApproved`, it is required.|
|assignmentState      |String|         | The state of assignment, and the values can be `Eligible` or `Active`. For decision of `AdminApproved`, it is required. |
### Response
This method can only be applied to requests that are in status of `PendingAdminDecision`.

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Example

### Request

<!-- {
  "blockType": "request",
  "name": "updaterequest_governanceroleassignmentrequest"
}-->
```http
POST https://graph.microsoft.com/beta/privilegedAccess/aadRoles/roleAssignmentRequests/7c53453e-d5a4-41e0-8eb1-32d5ec8bfdee/updateRequest
```

### Request body

```json
{
  "reason":"approve the request to extend role assignment",
  "schedule":{
    "type":"Once",
    "startDateTime":"2018-02-20T07:31:13.451Z",
    "stopDateTime":"2018-05-21T07:31:13.451Z",
    },
  "decision":"AdminApproved",
  "assignmentState": "Eligible"
}
```

##### Response
<!-- {
  "blockType": "response",
  "@odata.type": "microsoft.graph.None"
} -->
```http
HTTP/1.1 204 No Content
```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "UpdateRequest governanceRoleAssignmentRequest",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
