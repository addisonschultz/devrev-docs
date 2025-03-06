# Get Artifact

```http
GET https://api.devrev.ai/artifacts.get
```

Gets the requested artifact's information.



## Query Parameters

- Id (required): The requested artifact's ID.
- Version (optional): The version of the artifact that needs to be fetched.

## Response Body

- 200: The response to getting an artifact's information.

## Examples

```shell
curl -G https://api.devrev.ai/artifacts.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```