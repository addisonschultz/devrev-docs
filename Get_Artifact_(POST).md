# Get Artifact (POST)

```http
POST https://api.devrev.ai/artifacts.get
Content-Type: application/json
```

Gets the requested artifact's information.



## Response Body

- 200: The response to getting an artifact's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/artifacts.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```