# Get Webhook

```http
GET https://api.devrev.ai/webhooks.get
```

Gets the requested webhook's information.



## Query Parameters

- Id (required): ID for the webhook.

## Response Body

- 200: The response to getting the information for the webhook.

## Examples

```shell
curl -G https://api.devrev.ai/webhooks.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```