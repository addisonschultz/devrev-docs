# Count Engagements

```http
GET https://api.devrev.ai/engagements.count
```

Counts the engagement records.



## Query Parameters

- ExternalRef (optional): Filters for meetings with the provided external_refs.
- Members (optional): Filters for engagement of the provided members.
- Parent (optional): Filters for engagements with the provided parent.
- Type (optional): Filters for engagement of the provided types.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/engagements.count \
     -H "Authorization: Bearer <token>"
```