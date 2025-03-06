# Authorize Keyrings (POST)

```http
POST https://api.devrev.ai/keyrings.authorize
Content-Type: application/json
```

OAuth2 authorization callback.



## Examples

```shell
curl -X POST https://api.devrev.ai/keyrings.authorize \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "code": "code",
  "state": "state"
}'
```