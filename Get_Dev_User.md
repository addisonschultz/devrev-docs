# Get Dev User

```http
GET https://api.devrev.ai/dev-users.get
```

Gets the requested user's information.



## Query Parameters

- Id (required): User ID of the requested Dev user.

## Response Body

- 200: The response to getting the information for the Dev user.

## Examples

```shell
curl -G https://api.devrev.ai/dev-users.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```