# List Links (POST)

```http
POST https://api.devrev.ai/links.list
Content-Type: application/json
```

Lists the available links.



## Response Body

- 200: The response to listing the links.

## Examples

```shell
curl -X POST https://api.devrev.ai/links.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "direction": "is_source",
  "mode": "after",
  "object": "object"
}'
```