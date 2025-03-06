# List Artifacts (POST)

```http
POST https://api.devrev.ai/artifacts.list
Content-Type: application/json
```

List the artifacts attached to an object.



## Response Body

- 200: The response to list artifacts attached to an object.

## Examples

```shell
curl -X POST https://api.devrev.ai/artifacts.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```