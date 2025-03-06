# Get States Custom

```http
GET https://api.devrev.ai/states.custom.get
```

Gets a custom state.



## Query Parameters

- Id (required): The ID of the custom state to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/states.custom.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```