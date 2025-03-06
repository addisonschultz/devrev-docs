# Update Command

```http
POST https://api.devrev.ai/commands.update
Content-Type: application/json
```

Updates a command.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/commands.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "action": {
    "action_details": {},
    "template_type": "devrev_v1"
  },
  "id": "id",
  "status": "disabled"
}'
```