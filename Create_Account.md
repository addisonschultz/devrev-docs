# Create Account

```http
POST https://api.devrev.ai/accounts.create
Content-Type: application/json
```

Creates an account, which is a record representing a customer or an
organization.




## Response Body

- 201: The response to creating a new account.

## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "display_name": "display_name"
}'
```