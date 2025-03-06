# Prepare-Update Schemas Subtypes

```http
POST https://api.devrev.ai/schemas.subtypes.prepare-update
Content-Type: application/json
```

Gets the new fragment IDs and fields resulting from changing a subtype.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.subtypes.prepare-update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "leaf_type": "leaf_type"
}'
```