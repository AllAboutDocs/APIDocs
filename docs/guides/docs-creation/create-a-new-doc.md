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

This guide explains how to create a new Docs object within the Docs ecosystem.  
Use this endpoint when onboarding new users or provisioning additional Docs containers for existing ones.

---

## Overview

A Docs object represents a user's document container.  
When you call this endpoint:

- If the **user does not exist**, a new user is created automatically using `externalId`.
- If the **user exists**, the Docs object links to an existing `owner.id`.

You must provide **either**:

- `owner.id`  
  **or**
- `externalId`

---

## When You Should Use This Endpoint

Use this API when:

- onboarding a new customer
- creating a Docs container for an existing customer
- linking third-party customer identifiers using `externalId`
- setting up onboarding flows that require Docs

---

## Prerequisites

Ensure you have the following before making a request:

- `Docs-Entity-ID` header
- `X-Idempotency-Key` header
- Docs type (`type`)
- One of:
  - `owner.id`
  - or `externalId`

---

## Step 1: Add Required Headers

| Header              | Required | Description                      |
| ------------------- | -------- | -------------------------------- |
| `Docs-Entity-ID`    | Yes      | Unique identifier of your entity |
| `X-Idempotency-Key` | Yes      | Prevents duplicate creations     |

---

## Step 2: Build the Request Body

Your JSON must include:

- The Docs `type`
- One identifier: `owner.id` or `externalId`

### Example

```json
{
  "type": "full",
  "owner": {
    "id": "0f5ly1v7p3gqj5ii56e6k6q61x",
    "externalId": "unique-customer-code"
  }
}
```
