# Get Dev User (POST)

```http
POST https://api.devrev.ai/dev-users.get
Content-Type: application/json
```

Gets the requested user's information.



## Response Body

- 200: The response to getting the information for the Dev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```