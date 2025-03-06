# Get Conversation (POST)

```http
POST https://api.devrev.ai/conversations.get
Content-Type: application/json
```

Gets the requested conversation's information.



## Response Body

- 200: The response to getting a conversation's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/conversations.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```