# Get Sla (POST)

```http
POST https://api.devrev.ai/slas.get
Content-Type: application/json
```

Gets an SLA.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/slas.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```