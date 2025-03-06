# Update Reaction

```http
POST https://api.devrev.ai/reactions.update
Content-Type: application/json
```

Updates a reaction for an object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/reactions.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "action": "add",
  "emoji": "emoji",
  "object": "object"
}'
```