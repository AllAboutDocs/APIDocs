## Retrieve Docs details by Docs ID

This request retrieves the details of a specific Docs by the Docs ID. The details can be retrieved using the following:

### Query parameters - Required\*

- `id` - the unique identifier created by Docs Service for each Docs object
- `Docs-Entity-ID` - the unique identifier of the third party entity

The retrieved response displays the details associated with the specified Docs ID.

**URL**

`{URL}/v1/docs/{id}`

**METHOD**

GET

**SUCCESS RESPONSE**

200: The Docs details for the requested ID are displayed.

**SAMPLE RESPONSE**

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
