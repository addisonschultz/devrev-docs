# Get Tag

```http
GET https://api.devrev.ai/tags.get
```

Gets a tag's information.



## Query Parameters

- Id (required): The requested tag's ID.

## Response Body

- 200: The response to getting a tag's information.

## Examples

```shell
curl -G https://api.devrev.ai/tags.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```