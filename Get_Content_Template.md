# Get Content Template

```http
GET https://api.devrev.ai/content-template.get
```

Get the content template.



## Query Parameters

- Id (required): The content template's ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/content-template.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```