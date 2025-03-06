# Get Rev User (POST)

```http
POST https://api.devrev.ai/rev-users.get
Content-Type: application/json
```

Returns the Rev user of a Rev organization by its ID.



## Response Body

- 200: The returned Rev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```