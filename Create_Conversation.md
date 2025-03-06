# Create Conversation

```http
POST https://api.devrev.ai/conversations.create
Content-Type: application/json
```

Creates a conversation.



## Response Body

- 201: The response to creating a new conversation.

## Examples

```shell
curl -X POST https://api.devrev.ai/conversations.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "support",
  "custom_schema_spec": {},
  "metadata": {},
  "stage": {}
}'
```