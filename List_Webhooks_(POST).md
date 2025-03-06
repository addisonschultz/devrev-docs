# List Webhooks (POST)

```http
POST https://api.devrev.ai/webhooks.list
Content-Type: application/json
```

Lists the webhooks.



## Response Body

- 200: The response to listing the webhooks.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```