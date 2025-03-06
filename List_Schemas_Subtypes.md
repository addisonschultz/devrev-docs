# List Schemas Subtypes

```http
GET https://api.devrev.ai/schemas.subtypes.list
```

Lists subtypes.



## Query Parameters

- LeafType (optional): Leaf type for which subtypes are required.
- LeafTypes (optional): List of leaf types for which subtypes are required.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/schemas.subtypes.list \
     -H "Authorization: Bearer <token>"
```