# List Groups (POST)

```http
POST https://api.devrev.ai/groups.list
Content-Type: application/json
```

Lists the available groups.



## Response Body

- 200: The response to listing the groups.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```