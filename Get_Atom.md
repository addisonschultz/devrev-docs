# Get Atom

```http
GET https://api.devrev.ai/atoms.get
```

Gets the specified object.



## Query Parameters

- Id (required): The ID of the object to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/atoms.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```