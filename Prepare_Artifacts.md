# Prepare Artifacts

```http
POST https://api.devrev.ai/artifacts.prepare
Content-Type: application/json
```

Creates an artifact and generates an upload URL for its data.




## Response Body

- 200: The response to preparing a URL to upload a file.

## Examples

```shell
curl -X POST https://api.devrev.ai/artifacts.prepare \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "file_name": "file_name"
}'
```