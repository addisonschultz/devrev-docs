# Get Schemas Custom

```http
GET https://api.devrev.ai/schemas.custom.get
```

Gets a custom schema fragment.



## Query Parameters

- Id (required): The ID of the custom schema fragment.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/schemas.custom.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```