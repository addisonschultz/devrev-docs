# Delete Part

```http
POST https://api.devrev.ai/parts.delete
Content-Type: application/json
```

Deletes a [part](https://devrev.ai/docs/product/parts).



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/parts.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```