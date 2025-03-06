# Get Link Types Custom

```http
GET https://api.devrev.ai/link-types.custom.get
```

Gets a custom link type.



## Query Parameters

- Id (required): The ID of the custom link type to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/link-types.custom.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```