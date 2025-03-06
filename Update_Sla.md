# Update Sla

```http
POST https://api.devrev.ai/slas.update
Content-Type: application/json
```

Updates a draft SLA.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/slas.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "account_selector": {
    "created_date": {},
    "modified_date": {}
  },
  "evaluation_period": "monthly",
  "id": "id"
}'
```