# List Accounts (POST)

```http
POST https://api.devrev.ai/accounts.list
Content-Type: application/json
```

Gets a list of accounts.



## Response Body

- 200: The response to listing all accounts matching the filter criteria.


## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {},
  "mode": "after",
  "modified_date": {}
}'
```