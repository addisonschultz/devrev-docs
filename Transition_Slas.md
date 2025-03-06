# Transition Slas

```http
POST https://api.devrev.ai/slas.transition
Content-Type: application/json
```

Changes the status of an SLA.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/slas.transition \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "status": "archived"
}'
```