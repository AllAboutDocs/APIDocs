# Retrieve docs details by external ID

This request retrieves the details of a single docs transfer by a specific external ID, for an existing Docs account. The details can be retrieved using the following:

**Query parameters - Required\***

- `externalId` - the unique identifier provided by the third party for each successful docs transfer

- `X-Docs-ID` - the unique customer Docs account ID

- `Docs-Entity-ID` - the unique identifier of the third party entity

The retrieved response displays the details of the docs transfer associated with the specified external ID.

**URL**

`{URL}/v1/docs/lists`

**METHOD**

GET

**SUCCESS RESPONSE**
200: The docs details for the requested ID are displayed.

**SAMPLE RESPONSE**

```JSON
[
{
"id":"789e4567-e89b-12d3-a456-426614178901",
"externalId": "1234hshs",
"type": "Orderrevert",
"description": "Full revert order - abgd-ouyg",
"status": "Completed",
"creationDateTime": "2023-12-01T00:00:00Z",
"amount": {
"value": 35.25,
"type": "SAR"
}
"transactionBreakdown": [
{
"referenceId": "RRN12345 ",
"docsMethod": "manual",
"amount": {
"value": 15,
"type": "SAR"
}
},
{
"referenceId": "RRN789",
"docsMethod": "online",
"amount": {
"value": 20.25,
"type": "SAR"
}
}
],
"metadata": {
"flow": "OrderrevertFull | OrderrevertPartial",
"field": "value"
}
}
]
```
