# Locate Artifacts (POST)

```http
POST https://api.devrev.ai/artifacts.locate
Content-Type: application/json
```

Gets the download URL for the artifact.



## Response Body

- 200: The response to getting an artifact's download URL.

## Examples

```shell
curl -X POST https://api.devrev.ai/artifacts.locate \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```