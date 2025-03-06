# Get Event Source

```http
GET https://api.devrev.ai/event-sources.get
```

Gets an event source.



## Query Parameters

- Id (required): The event source's ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/event-sources.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```