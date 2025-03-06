# List Reactions (POST)

```http
POST https://api.devrev.ai/reactions.list
Content-Type: application/json
```

Lists the reactors for an object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/reactions.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "emoji": "emoji",
  "object": "object"
}'
```