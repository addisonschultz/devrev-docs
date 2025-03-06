# Self Dev User (POST)

```http
POST https://api.devrev.ai/dev-users.self
Content-Type: application/json
```

Gets the authenticated user's information.



## Response Body

- 200: The response to getting the information for the authenticated user.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.self \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```