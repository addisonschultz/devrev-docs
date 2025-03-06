# Locate Artifacts

```http
GET https://api.devrev.ai/artifacts.locate
```

Gets the download URL for the artifact.



## Query Parameters

- Id (required): The ID of the artifact to get the URL for.
- Version (optional): The version of the artifact that needs to be fetched.

## Response Body

- 200: The response to getting an artifact's download URL.

## Examples

```shell
curl -G https://api.devrev.ai/artifacts.locate \
     -H "Authorization: Bearer <token>" \
     -d id=id
```