# Delete Webhook

```http
POST https://api.devrev.ai/webhooks.delete
Content-Type: application/json
```

Deletes the requested webhook.



## Response Body

- 200: The response to deleting the webhook.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```