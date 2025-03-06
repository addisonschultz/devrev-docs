# Get Account (POST)

```http
POST https://api.devrev.ai/accounts.get
Content-Type: application/json
```

Retrieves an account's information.



## Response Body

- 200: The returned account.

## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```