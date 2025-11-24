# Update Docs status

This request updates the Docs status. The various Docs statuses are described below:

- **Active** - The Docs account is active and is fully operational. All Docs activity is operational.

- **Pending** - The Docs account is pending and is partially operational. Docs activity related to lists will be pending.

- **Blocked** - The Docs account is blocked and is fully non-operational.

The Docs status is updated using the following:

**Query parameters - Required\***

- id - the unique internal identifier of the Docs to update
- Docs-Entity-ID - the unique identifier of the third party entity

**Request Parameters - Required\***

- path - the property to be updated, e.g. status
- op - the operation to be performed, e.g. replace
- value - the status to be applied, e.g. block

**URL**

`{URL}/v1/docs/{id}`

**METHOD**

PATCH

**SUCCESS RESPONSE**

200: The Docs status is updated.

**SAMPLE REQUEST**

```JSON
[
{
"path": "/status",
"op": "replace",
"value": "block"
}
]
```

**_SAMPLE RESPONSE_**

```JSON
{
"id": "0f5w7ir5wcqj8ydeih3wpv0807",
"status": "Created",
"owner": {
"id": "0f5w7ir5wcqj8ydeih3wpv0807",
"type": "User",
"externalId": "sample"
}
}
```
