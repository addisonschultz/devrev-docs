# Get Code Change

```http
GET https://api.devrev.ai/code-changes.get
```

Gets a code change object.



## Query Parameters

- Id (required): The code change object ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/code-changes.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```