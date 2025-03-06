# Delete Auth Token

```http
POST https://api.devrev.ai/auth-tokens.delete
Content-Type: application/json
```

Revokes the token that matches the given token ID issued under the
given Dev organization.




## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```