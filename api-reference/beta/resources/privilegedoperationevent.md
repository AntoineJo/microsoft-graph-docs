---
title: "privilegedOperationEvent resource type"
description: "Represents an audit event that is generated by Privileged Identity Management for the role operations, such as an administrator manages privileged roles, a user activates his role, and a user deactivates his role."
localization_priority: Normal
doc_type: resourcePageType
ms.prod: ""
author: ""
---

# privilegedOperationEvent resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an audit event that is generated by Privileged Identity Management for the role operations, such as an administrator manages privileged roles, a user activates his role, and a user deactivates his role.


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List privilegedOperationEvent](../api/privilegedoperationevent-list.md) | [privilegedOperationEvent](privilegedoperationevent.md) collection. |Get collection of privilegedOperationEvent objects.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|additionalInformation|string|Detailed human readable information for the event.|
|creationDateTime|dateTimeOffset|Indicates the time when the event is created.|
|expirationDateTime|dateTimeOffset|This is only used when the requestType is "Activate", and it indicates the expiration time for the role activation.|
|id|string|The unique identifier for privilegedOperationEvent. Read-only.|
|referenceKey|string|Incident/Request ticket number during role activation. The value is presented only if the ticket number is provided during role activation.|
|referenceSystem|string|Incident/Request ticketing system provided during tole activation. The value is presented only if the ticket system is provided during role activation.|
|requestType|string|The request operation type. The requestType value can be: ```Assign``` (role assignment), ```Activate``` (role activation), ```Unassign``` (remove role assignment), ```Deactivate``` (role deactivation), ```ScanAlersNow``` (scan security alerts), ```DismissAlert``` (dismiss security alert), ```FixAlertItem``` (fix a security alert issue), ```AccessReview_Review``` (review an Access Review), ```AccessReview_Create``` (create an Access Review), ```AccessReview_Update``` (update an Access Review), and ```AccessReview_Delete``` (delete an Access Review).|
|requestorId|string|The user id of the requestor who initiates the operation.|
|requestorName|string|The user name of the requestor who initiates the operation.|
|roleId|string|The id of the role that is associated with the operation.|
|roleName|string|The name of the role.|
|tenantId|string|The tenant (organization) id.|
|userId|string|The id of the user that is associated with the operation.|
|userMail|string|The user's email.|
|userName|string|The user's display name.|

## Relationships
None


## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.privilegedOperationEvent"
}-->

```json
{
  "additionalInformation": "string",
  "creationDateTime": "String (timestamp)",
  "expirationDateTime": "String (timestamp)",
  "id": "string (identifier)",
  "requestType": "string",
  "requestorId": "string",
  "requestorName": "string",
  "roleId": "string",
  "roleName": "string",
  "tenantId": "string",
  "userId": "string",
  "userMail": "string",
  "userName": "string",
  "referenceKey": "string",
  "referenceSystem": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "privilegedOperationEvent resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->