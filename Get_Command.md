# Get Command

```http
GET https://api.devrev.ai/commands.get
```

Gets a command.



## Query Parameters

- Id (required): The command's ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/commands.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```