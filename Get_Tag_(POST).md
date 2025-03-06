# Get Tag (POST)

```http
POST https://api.devrev.ai/tags.get
Content-Type: application/json
```

Gets a tag's information.



## Response Body

- 200: The response to getting a tag's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/tags.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```