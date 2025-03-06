# Get Directory

```http
GET https://api.devrev.ai/directories.get
```

Gets the specified directory.



## Query Parameters

- Id (required): The ID of the requested directory.

## Response Body

- 200: Get directory response.

## Examples

```shell
curl -G https://api.devrev.ai/directories.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```