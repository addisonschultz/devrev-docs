# Get Command (POST)

```http
POST https://api.devrev.ai/commands.get
Content-Type: application/json
```

Gets a command.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/commands.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```