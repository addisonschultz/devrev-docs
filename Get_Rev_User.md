# Get Rev User

```http
GET https://api.devrev.ai/rev-users.get
```

Returns the Rev user of a Rev organization by its ID.



## Query Parameters

- Id (required): The ID of Rev user to be retrieved.

## Response Body

- 200: The returned Rev user.

## Examples

```shell
curl -G https://api.devrev.ai/rev-users.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```