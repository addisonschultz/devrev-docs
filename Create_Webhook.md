# Create Webhook

```http
POST https://api.devrev.ai/webhooks.create
Content-Type: application/json
```

Creates a new webhook target.



## Response Body

- 201: The response to creating a new webhook.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "url": "url"
}'
```