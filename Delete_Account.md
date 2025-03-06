# Delete Account

```http
POST https://api.devrev.ai/accounts.delete
Content-Type: application/json
```

Deletes an account.



## Response Body

- 200: The response to deleting an account.

## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```