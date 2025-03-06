# List Stage Diagrams (POST)

```http
POST https://api.devrev.ai/stage-diagrams.list
Content-Type: application/json
```

Lists stage diagrams.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stage-diagrams.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```