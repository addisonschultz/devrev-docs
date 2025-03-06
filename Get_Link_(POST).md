# Get Link (POST)

```http
POST https://api.devrev.ai/links.get
Content-Type: application/json
```

Gets the requested link's information.



## Response Body

- 200: The response to getting a link's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/links.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```