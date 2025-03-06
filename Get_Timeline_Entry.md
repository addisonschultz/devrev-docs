# Get Timeline Entry

```http
GET https://api.devrev.ai/timeline-entries.get
```

Gets an entry on an object's timeline.



## Query Parameters

- Id (required): The ID of the timeline entry to get.

## Response Body

- 200: The request to getting a timeline entry.

## Examples

```shell
curl -G https://api.devrev.ai/timeline-entries.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```