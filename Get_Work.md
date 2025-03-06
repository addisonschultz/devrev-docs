# Get Work

```http
GET https://api.devrev.ai/works.get
```

Gets a work item's information.



## Query Parameters

- Id (required): The work's ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/works.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```