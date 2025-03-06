# Get Part

```http
GET https://api.devrev.ai/parts.get
```

Gets a [part's](https://devrev.ai/docs/product/parts) information.




## Query Parameters

- Id (required): The ID of the part to retrieve.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/parts.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```