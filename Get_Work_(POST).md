# Get Work (POST)

```http
POST https://api.devrev.ai/works.get
Content-Type: application/json
```

Gets a work item's information.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/works.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```