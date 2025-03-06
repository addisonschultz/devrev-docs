# Update Account

```http
POST https://api.devrev.ai/accounts.update
Content-Type: application/json
```

Updates an account's information.



## Response Body

- 200: Updated account object.

## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "websites": {}
}'
```