# Get Incident

```http
GET https://api.devrev.ai/incidents.get
```

Gets an incident.



## Query Parameters

- Id (required): The ID of the incident to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/incidents.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```