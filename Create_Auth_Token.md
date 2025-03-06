# Create Auth Token

```http
POST https://api.devrev.ai/auth-tokens.create
Content-Type: application/json
```

Creates a JWT corresponding to the requested token type for the
authenticated user.




## Response Body

- 201: Response for the request to create a new token corresponding to the
requested token type.


## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "grant_type": "urn:devrev:params:oauth:grant-type:token-issue",
  "requested_token_type": "urn:devrev:params:oauth:token-type:aat",
  "rev_info": {
    "account_traits": {},
    "org_traits": {},
    "user_traits": {},
    "workspace_traits": {}
  },
  "subject_token_type": "urn:devrev:params:oauth:token-type:jwt:auth0"
}'
```