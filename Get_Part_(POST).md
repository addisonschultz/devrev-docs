# Get Part (POST)

```http
POST https://api.devrev.ai/parts.get
Content-Type: application/json
```

Gets a [part's](https://devrev.ai/docs/product/parts) information.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/parts.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```