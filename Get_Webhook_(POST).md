# Get Webhook (POST)

```http
POST https://api.devrev.ai/webhooks.get
Content-Type: application/json
```

Gets the requested webhook's information.



## Response Body

- 200: The response to getting the information for the webhook.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```