# Create Sla

```http
POST https://api.devrev.ai/slas.create
Content-Type: application/json
```

Creates an SLA in draft status.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/slas.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "account_selector": {
    "created_date": {},
    "modified_date": {}
  },
  "evaluation_period": "monthly",
  "name": "name",
  "sla_type": "external"
}'
```