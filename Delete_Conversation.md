# Delete Conversation

```http
POST https://api.devrev.ai/conversations.delete
Content-Type: application/json
```

Deletes the requested conversation.



## Response Body

- 200: The response for deleting a conversation.

## Examples

```shell
curl -X POST https://api.devrev.ai/conversations.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```