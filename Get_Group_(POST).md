# Get Group (POST)

```http
POST https://api.devrev.ai/groups.get
Content-Type: application/json
```

Gets the requested group.



## Response Body

- 200: The response to getting the group.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```