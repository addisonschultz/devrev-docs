# Get Stage Diagram (POST)

```http
POST https://api.devrev.ai/stage-diagrams.get
Content-Type: application/json
```

Gets a stage diagram.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stage-diagrams.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```