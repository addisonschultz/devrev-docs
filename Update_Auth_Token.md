# Update Auth Token

```http
POST https://api.devrev.ai/auth-tokens.update
Content-Type: application/json
```

Updates token metadata of a token issued under a given Dev
organization.




## Response Body

- 200: Response for the request to update the token metadata.

## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "token_hint": "token_hint",
  "token_id": "token_id"
}'
```