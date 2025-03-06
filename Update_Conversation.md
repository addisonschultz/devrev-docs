# Update Conversation

```http
POST https://api.devrev.ai/conversations.update
Content-Type: application/json
```

Updates the requested conversation.



## Response Body

- 200: The response for updating a conversation.

## Examples

```shell
curl -X POST https://api.devrev.ai/conversations.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "applies_to_parts": {},
  "custom_schema_spec": {},
  "id": "id",
  "members": {},
  "metadata": {},
  "owned_by": {},
  "stage": {},
  "tags": {},
  "user_sessions": {}
}'
```