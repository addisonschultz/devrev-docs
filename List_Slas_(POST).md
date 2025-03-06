# List Slas (POST)

```http
POST https://api.devrev.ai/slas.list
Content-Type: application/json
```

Lists SLAs matching a filter.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/slas.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "applies_to_op": "all",
  "mode": "after"
}'
```