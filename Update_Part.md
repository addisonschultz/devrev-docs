# Update Part

```http
POST https://api.devrev.ai/parts.update
Content-Type: application/json
```

Updates a [part's](https://devrev.ai/docs/product/parts) information.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/parts.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "capability"
}'
```