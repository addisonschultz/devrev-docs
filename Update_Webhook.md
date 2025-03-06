# Update Webhook

```http
POST https://api.devrev.ai/webhooks.update
Content-Type: application/json
```

Updates the requested webhook.



## Response Body

- 200: The response to updating the webhook.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "action": "activate",
  "event_types": {},
  "id": "id"
}'
```