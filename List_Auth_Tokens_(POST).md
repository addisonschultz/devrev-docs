# List Auth Tokens (POST)

```http
POST https://api.devrev.ai/auth-tokens.list
Content-Type: application/json
```

Gets the token metadata for all the tokens corresponding to the given
token type issued for a given subject.




## Response Body

- 200: The response to list the token metadata.

## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "requested_token_type": "urn:devrev:params:oauth:token-type:aat"
}'
```