# Get Engagement

```http
GET https://api.devrev.ai/engagements.get
```

Gets the engagement record.



## Query Parameters

- Id (required): The engagement ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/engagements.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```