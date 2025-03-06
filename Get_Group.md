# Get Group

```http
GET https://api.devrev.ai/groups.get
```

Gets the requested group.



## Query Parameters

- Id (required): The ID of the group to get.

## Response Body

- 200: The response to getting the group.

## Examples

```shell
curl -G https://api.devrev.ai/groups.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```