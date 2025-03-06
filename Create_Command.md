# Create Command

```http
POST https://api.devrev.ai/commands.create
Content-Type: application/json
```

Creates a command.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/commands.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "action": {
    "action_details": {},
    "executor_type": "rego",
    "template_type": "devrev_v1"
  },
  "name": "name",
  "namespace": "namespace",
  "status": "disabled"
}'
```