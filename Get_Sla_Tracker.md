# Get Sla Tracker

```http
GET https://api.devrev.ai/sla-trackers.get
```

Gets an SLA tracker.



## Query Parameters

- Id (required): The ID of the SLA tracker to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/sla-trackers.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```