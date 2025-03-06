# Authorize Keyrings

```http
GET https://api.devrev.ai/keyrings.authorize
```

OAuth2 authorization callback.



## Query Parameters

- Code (required): Code to exchange for an access token.
- State (required): State value given to the authorization request.

## Examples

```shell
curl -G https://api.devrev.ai/keyrings.authorize \
     -H "Authorization: Bearer <token>" \
     -d code=code \
     -d state=state
```