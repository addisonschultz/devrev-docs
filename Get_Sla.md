# Get Sla

```http
GET https://api.devrev.ai/slas.get
```

Gets an SLA.



## Query Parameters

- Id (required): The ID of the SLA to get.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/slas.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```