# Create a new Doc

This request creates a new Docs account in the Docs ecosystem and establishes a docs container for a user. A user can have one or more docs, each identified by a unique Docs ID, linked user ID, and type.
This endpoint creates a Docs object depending on whether an existing user is available. The following two scenarios are possible:

- **User does not exist** - The user will be created in this flow by providing the external user id (third party-side customer code) and then passing the `X-User-Id` value in the header during Docs creation.

- **User already exists** - The Docs is created by providing an internal user Id or owner ID.  
  Note: You **must** provide either owner ID or external ID in the request body.

- The Create Docs request object **must** contain the following:

**Query Parameters - Required\***

- `Docs-Entity-ID` - the unique identifier of the third party entity
- `X-Idempotency-Key` - the unique server-created key to confirm subsequent retries of the same request

**Request Parameters - Required\***

- `type` - the type of the Docs to be created
- `owner`
  - `id` - the unique ID of the Docs owner
- `externalId`- the unique customer code of of Docs user

**URL**

`{URL}v1/docs`

**METHOD**

POST

**SUCCESS RESPONSE**

201: The Docs object is created.

**SAMPLE REQUEST**

```JSON
{
"type": "full",
"owner" {
"type": "User"
"id": "0f5ly1v7p3gqj5ii56e6k6q61x"
"externalId": "unique-customer-code"
}
}
```

**SAMPLE RESPONSE**

```JSON
{
    "id": "asa0a98d0sa8d0sa9d8saasdsa9",
    "status": "created | active | locked | terminated",
    "owner" {
   "type": "User"
   "id": "0f5ly1v7p3gqj5ii56e6k6q61x"
   "externalId": "unique-customer-code"
 }
}

```
