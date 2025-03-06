# Delete Auth Tokens Self

```http
POST https://api.devrev.ai/auth-tokens.self.delete
Content-Type: application/json
```

Revokes all the tokens that matches the given token type created by the
authenticated user.




## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.self.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "requested_token_type": "urn:devrev:params:oauth:token-type:aat"
}'
```