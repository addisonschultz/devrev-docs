# List Commands (POST)

```http
POST https://api.devrev.ai/commands.list
Content-Type: application/json
```

Lists commands for a Dev organization.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/commands.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```