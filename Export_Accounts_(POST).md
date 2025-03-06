# Export Accounts (POST)

```http
POST https://api.devrev.ai/accounts.export
Content-Type: application/json
```

Exports a collection of accounts.



## Response Body

- 200: The response to exporting a collection of accounts.

## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.export \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {},
  "modified_date": {}
}'
```