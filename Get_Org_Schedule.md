# Get Org Schedule

```http
GET https://api.devrev.ai/org-schedules.get
```

Gets an organization schedule.



## Query Parameters

- Id (required): Organization schedule ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/org-schedules.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```