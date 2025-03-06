# Assign Slas

```http
POST https://api.devrev.ai/slas.assign
Content-Type: application/json
```

 Assigns the SLA to a set of Rev organizations.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/slas.assign \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "rev_orgs": [
    "rev_orgs",
    "rev_orgs"
  ]
}'
```