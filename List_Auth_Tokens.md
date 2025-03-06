# List Auth Tokens

```http
GET https://api.devrev.ai/auth-tokens.list
```

Gets the token metadata for all the tokens corresponding to the given
token type issued for a given subject.




## Query Parameters

- ClientId (optional): An identifier that represents the application, which requested the
token. Only relevant for application access tokens.

- RequestedTokenType (required): The type of the requested token. If no value is specified, the
response will include tokens of all the types.

- Subject (optional): The subject associated with the token. In the absence of this
parameter, the ID of the authenticated entity is treated as the
subject.


## Response Body

- 200: The response to list the token metadata.

## Examples

```shell
curl -G https://api.devrev.ai/auth-tokens.list \
     -H "Authorization: Bearer <token>" \
     --data-urlencode requested_token_type=urn:devrev:params:oauth:token-type:aat
```