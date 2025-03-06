# Get Service Account (POST)

```http
POST https://api.devrev.ai/service-accounts.get
Content-Type: application/json
```

Gets a service account.



## Response Body

- 200: The response object that carries the service account's information
corresponding to the request.


## Examples

```shell
curl -X POST https://api.devrev.ai/service-accounts.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```