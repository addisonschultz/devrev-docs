# Get Link

```http
GET https://api.devrev.ai/links.get
```

Gets the requested link's information.



## Query Parameters

- Id (required): The requested link's ID.

## Response Body

- 200: The response to getting a link's information.

## Examples

```shell
curl -G https://api.devrev.ai/links.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```