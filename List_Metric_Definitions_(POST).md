# List Metric Definitions (POST)

```http
POST https://api.devrev.ai/metric-definitions.list
Content-Type: application/json
```

Lists metric definitions matching a filter.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/metric-definitions.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```