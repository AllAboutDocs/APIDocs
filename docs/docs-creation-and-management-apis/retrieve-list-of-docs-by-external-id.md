# Retrieve a list of docs by external ID

This request retrieves the list of docs by external ID. The details can be retrieved using the following:

**Query parameters - Required\***

- `externalId` - the unique identifier provided by the third party for each Docs object
- `Docs-Entity-ID` - the unique identifier of the third party entity
  The retrieved response displays the details of all docs associated with the specified external ID, including the Docs status, owner ID, and type.

**URL**

`{URL}/v1/docs`

**METHOD**

GET

**SUCCESS RESPONSE**

200: The list of docs is displayed.

**SAMPLE RESPONSE**

```JSON
[
  {
  "id": "0f5w7ir5wcqj8ydeih3wpv0807",
  "status": "Created",
  "owner": {
  "id": "0f5w7ir5wcqj8ydeih3wpv0807",
  "type": "User",
  "externalId": "sample"
  }
  }
  ]
```
