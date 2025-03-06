# Get Meeting

```http
GET https://api.devrev.ai/meetings.get
```

Gets the meeting record.



## Query Parameters

- Id (required): The meeting's ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/meetings.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```