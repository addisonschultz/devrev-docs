# List Artifacts

```http
GET https://api.devrev.ai/artifacts.list
```

List the artifacts attached to an object.



## Query Parameters

- ParentId (optional): The ID of the object to filter artifacts.

## Response Body

- 200: The response to list artifacts attached to an object.

## Examples

```shell
curl https://api.devrev.ai/artifacts.list \
     -H "Authorization: Bearer <token>"
```