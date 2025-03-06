# Create Part

```http
POST https://api.devrev.ai/parts.create
Content-Type: application/json
```

Creates new [part](https://devrev.ai/docs/product/parts).



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/parts.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "capability",
  "parent_part": [
    "parent_part",
    "parent_part"
  ]
}'
```