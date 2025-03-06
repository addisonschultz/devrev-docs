# Update Stage Diagram

```http
POST https://api.devrev.ai/stage-diagrams.update
Content-Type: application/json
```

Updates a stage diagram.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stage-diagrams.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```