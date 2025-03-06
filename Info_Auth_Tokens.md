# Info Auth Tokens

```http
GET https://api.devrev.ai/auth-tokens.info
```

Returns the Dev organization, user and token attributes extracted from
the auth token.




## Response Body

- 200: The Dev organization, user and token attributes extracted from the auth
token.


## Examples

```shell
curl https://api.devrev.ai/auth-tokens.info \
     -H "Authorization: Bearer <token>"
```