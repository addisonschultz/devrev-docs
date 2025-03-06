# Get Stages Custom

```http
GET https://api.devrev.ai/stages.custom.get
```

Gets a custom stage.



## Query Parameters

- Id (required): The ID of the custom stage to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/stages.custom.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```