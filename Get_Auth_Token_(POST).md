# Get Auth Token (POST)

```http
POST https://api.devrev.ai/auth-tokens.get
Content-Type: application/json
```

Gets the token metadata corresponding to the given token ID under the
given Dev organization.




## Response Body

- 200: The response to get the token metadata.

## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "token_id": "token_id"
}'
```