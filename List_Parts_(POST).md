# List Parts (POST)

```http
POST https://api.devrev.ai/parts.list
Content-Type: application/json
```

Lists a collection of [parts](https://devrev.ai/docs/product/parts).




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/parts.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
  "parent_part": {
    "parts": [
      "parts",
      "parts"
    ]
  }
}'
```